https://youtu.be/Mz8s0XRMTwQ
<img width="1917" height="1020" alt="image" src="https://github.com/user-attachments/assets/4a312092-4473-4a04-99fe-6e719a6d0134" />


一、 製作流程
專案建立與 3D 模型匯入 :
在 Unity 中開啟新的 3D 專案，並匯入訓練家、寶可夢、精靈球三個 3D 模型。  
透過右側 Inspector 面板的 Materials 分頁解壓縮模型材質與貼圖（並確認材質球使用 Lit Shader 正常顯示外觀色彩）。
調整三者位置與縮放比例：將訓練家置於畫面右側、寶可夢置於畫面左側，精靈球放置於訓練家身旁作為拋出起點，並設定 Main Camera 角度以完整涵蓋由右至左的拋物線視野。

自然環境與地形建置（山脈、草地、樹木）:
背景起伏的山：使用 Raise or Lower Terrain 工具在場景後方繪製高低起伏的山脈輪廓，並以 Smooth Height 修飾山坡線條。 
草地與地表：切換至 Paint Terrain > Paint Texture，建立多組 Terrain Layer 圖層，先鋪設泥土／岩石作為基礎底色，再於地面局部刷上草地貼圖並調整 Tiling 紋理大小。  
樹木配置：點選 Paint Trees 工具載入樹木模型 Prefab，於草地與山腳周圍種植樹木以增加場景層次。

碰撞偵測與收服特效設定:
碰撞器設定：為寶可夢物件加入 Capsule Collider、勾選 Is Trigger 並將 Tag 設為 Pokemon；為精靈球加入 Sphere Collider 與 Rigidbody（取消勾選 Use Gravity，避免重力影響程式控制的拋物線軌跡）。
粒子特效製作：新增 Particle System（命名為 CaptureEffect），調整粒子顏色、發射數量與擴散速度營造收服閃光效果，並取消勾選 Looping 與 Play On Awake，使其僅在擊中目標瞬間播放一次。

二、 相關操作說明啟動專案：
開啟 Unity 專案與主場景後，點擊視窗上方中央的 Play（執行） 按鈕進入運行模式。
畫面配置檢視：進入畫面後，左側為訓練家與待命的精靈球，右側為目標寶可夢，背景包含起伏山脈、草地與樹木。  
拋出精靈球：按下鍵盤 Space（空白鍵），右側的精靈球會自動以拋物線軌跡由右至左飛向右側寶可夢，飛行期間球體會持續旋轉。  
收服與特效觸發：精靈球擊中寶可夢的瞬間，撞擊位置會釋放粒子收服特效，同時寶可夢消失，表示成功收服。
