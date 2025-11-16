// SoundCloud Go+ Unlock Script
// Mô-đun này được thiết kế để sửa đổi phản hồi API của SoundCloud
// nhằm kích hoạt các tính năng của SoundCloud Go+.

// Lấy nội dung phản hồi (response body) từ máy chủ.
var body = $response.body;
// Chuyển đổi nội dung từ chuỗi JSON sang đối tượng JavaScript để xử lý.
var obj = JSON.parse(body);

// Ghi đè thông tin gói đăng ký (plan)
// Đặt tài khoản ở mức "high_tier" (SoundCloud Go+)
obj.plan = {
    "vendor": "apple",
    "id": "high_tier",
    "manageable": true,
    "plan_upsells": [],
    "plan_id": "go-plus",
    "upsells": [],
    "plan_name": "SoundCloud Go+"
};

// Ghi đè danh sách các tính năng (features)
// Bật các tính năng trả phí và tắt quảng cáo.
obj.features = [
    {
        "name": "offline_sync", // Tải nhạc offline
        "enabled": true,
        "plans": ["mid_tier", "high_tier"]
    },
    {
        "name": "no_audio_ads", // Không có quảng cáo âm thanh
        "enabled": true,
        "plans": ["mid_tier", "high_tier"]
    },
    {
        "name": "hq_audio", // Âm thanh chất lượng cao
        "enabled": true,
        "plans": ["high_tier"]
    },
    // Đã sửa lỗi cú pháp ở đây:
    {
        "name": "system_playlist_in_library",
        "enabled": true,
        "plans": []
    },
    {
        "name": "ads_krux", // Tắt quảng cáo Krux
        "enabled": false,
        "plans": []
    },
    {
        "name": "new_home",
        "enabled": true,
        "plans": []
    },
    {
        "name": "spotlight", // Tắt quảng cáo spotlight
        "enabled": false,
        "plans": []
    }
];

// Chuyển đổi đối tượng JavaScript đã sửa đổi trở lại thành chuỗi JSON.
body = JSON.stringify(obj);
// Hoàn tất và gửi phản hồi đã bị sửa đổi về ứng dụng.
$done({ body });
