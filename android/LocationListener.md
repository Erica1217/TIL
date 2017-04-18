# 왜?
엄쌤 프로젝트에서 위치정보를 알아내야했다.

# LocationListener
안드로이드에서 위치정보를 알아내는 클래스이다.

# 예제
```
LocationListener locationListener = new LocationListener() {
        public void onLocationChanged(Location location) {
        Log.d("test", "onLocationChanged, location:" + location);
        double longitude = location.getLongitude(); //경도
        double latitude = location.getLatitude();   //위도
        double altitude = location.getAltitude();   //고도
        float accuracy = location.getAccuracy();    //정확도
        String provider = location.getProvider();   //위치제공자
        //Gps 위치제공자에 의한 위치변화. 오차범위가 좁다.
        //Network 위치제공자에 의한 위치변화
        //Network 위치는 Gps에 비해 정확도가 많이 떨어진다.
        }

        public void onStatusChanged(String provider, int status, Bundle extras) {
            logView.setText("onStatusChanged");
        }

        public void onProviderEnabled(String provider) {
            logView.setText("onProviderEnabled");
        }

        public void onProviderDisabled(String provider) {
            logView.setText("onProviderDisabled");
        }
    <!--};-->
```
## public void onLocationChanged(Location location)
이 함수는 기기의 위치가 바뀔때마다 호출되는 함수이다.


## onStatusChanged

## onProviderEnabled

## onProviderDisabled

# location.getAccuracy (정확도)
정확도는 숫자가 클 수록 좋은 것이 아니다. 숫자가 클 수록 정확도가 떨어지는 것이다. 예를들어, 
<br>
<br>
정확도가 50이라면 50m 반경으로 오차가 있을수 있다는 뜻이다. 그러니까 작을수록 좋은 것이다.

# location.getProvider (위치제공자)

# 위치정보 수신 중지
위치정보가 더 이상 필요없다면, 위치정보 업데이트를 중단하여 배터리소모를 줄여야한다. 기기의 위치가 바뀔때마다 호출되므로 비용이 비쌀 것으로 예상된다.

>public void removeUpdates (LocationListener listener)


# 출처
http://j07051.tistory.com/333 [흘러간다...]