コードの説明を以下に示す。
import cv2//cv2モジュールをインポートする。
capture = cv2.VideoCapture(0)//cv2.VideoCapture() で VideoCapture オブジェクトを取得。引数には撮影に使用するカメラのデバイス番号を入力する。コンピュータにカメラが1台だけしか接続されていないため0を入力。
while(True)://カメラから連続的に画像を取得するため、ここでは while 文で繰り返し処理を行う。
ret, frame = capture.read()//カメラから1コマのデータを取得するため capture.read() を呼び出しており、取得した画像データは変数 frame に代入されている。
cv2.imshow('frame',frame)//OSのフレームに画像を表示する。 cv2.imshow() メソッドを用いて画面に表示する。第一引数は開くフレームの名前を指定し、第二引数には、capture.read() で取得した画像データを指定する。
if cv2.waitKey(1) & 0xFF == ord('q'):   break//「q」キーがタイプされるとループを抜けるために break する。
capture.release()//VideoCapture を終了する。
cv2.destroyAllWindows()//開いたウィンドウを終了する。
