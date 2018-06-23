import cv2//open cvをpythonで実行するためのコード

capture = cv2.VideoCapture(0)//動画を撮影するためにVideoCapture型のオブジェクトを生成している。引数には撮影に使用するカメラのデバイス番号の0を入力。

while(True):
    ret, frame = capture.read()
    cv2.imshow('frame',frame)
    if cv2.waitKey(1) & 0xFF == ord('q'):
        break

capture.release()
cv2.destroyAllWindows()
