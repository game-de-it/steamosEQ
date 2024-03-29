# SteamOS EQ
## ●概要  
※2023年11月18日以前のsteamOSのバージョンの場合、正常に動作しない可能性がありますので最新版にバージョンアップしてください  

SteamOSで動作しているpipewireのフィルター機能を利用して、イコライザーを実装するスクリプトです。  
低音強調とシャリ感を弱めたチューニングになってます。  
手がビリビリするほどの低音をお楽しみください。  
なお、このEQはsteamdeckのスピーカー用にチューニングしてあるので、イヤホンジャックからは音が再生されないようになってます。  
イヤホンをお使いの場合はEQをオフ（デフォルト(スピーカー)）に切り替えてください。  
## ●手順  
  
1. steamdeckのデスクトップモードでブラウザを開き、上記「eq.sh.txt」をクリック  
　　
2. Rawをクリック  
![s1-2](/asset/s1-2.png)  
　　
3. 空いている場所で右クリックして「Save Page As」をクリック  
![s2](/asset/s2.png)  
  
4. Saveをクリック  
![s3-2](/asset/s3-2.png)  
  
5. ファイルブラウザでDownloadsディレクトリに移動して、eq.sh.txtを右クリックして「Open terminal Here」をクリック  
![s4-2](/asset/s4-2.png)  
  
6. `sh eq.sh.txt` と入力してエンター
![s5-2](/asset/s5-2.png)  
  
7. steamOSを再起動する  
  
8. steamボタン→オーディオ→出力デバイスから「effect_input.eq6」を選択するとEQがONになります  
※最新版のsteamOSだとイコライザのON設定が維持されなくなりましたので、お手数ですがsteamdeckを起動するたびにEQをONにしてください

![s6](/asset/s6.jpg)  
  
## ●EQチューニング方法(音質を調整したい方向けの情報)
デスクトップモードにて`~/.config/pipewire/pipewire.conf.d/sink-eq6.conf`ファイルをメモ帳などで開いてパラメータを編集します。  
基本的にいじる箇所は`control = { "Freq" = 100.0 "Q" = 1.0 "Gain" = 0.0 }`のような箇所になります。  
パラメータの変更後はOSを再起動するか、gamepaduiモードに移行すると設定が反映されます。  
  
* Freq  
変化させる周波数(Hz)です。  
(Freqを0にしてGainを上げるとプリアンプのような働きになります。)  
  
* Q  
Freqで設定した周波数を中心に前後どれくらいの周波数を巻き込んで変化させるかの値です。  
Q値が高いほど影響を受ける帯域幅は狭くなります。  
例えばQ値を4.3などにすると帯域幅は非常に狭くなるため、不自然に聞こえる可能性があります。  
(Q値を高くしてGainを下げることで特定の周波数をピンポイントで減らし、ノイズフィルターのような感じにも使えます)  
0.6から1.0の間のかなり穏やかな値で設定すると良い感じになります。  
  
* Gain  
増幅値で-10〜20までの間で設定します。



以上
