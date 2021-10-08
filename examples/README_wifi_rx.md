<h1>wifi_rx</h1>
<h2>UHD: USRP Source</h2>
USRP 장치에서 샘플을 스트리밍하는 데 사용(수신기 역할)</br>
스로틀 역할</br>
(Throttle:평균 속도가 특정 속도를 초과하지 않도록 샘플의 스로틀 흐름)</br>
</br>

<h3>Sync</h3>
USRP가 PC의 클럭 또는 PPS 신호가 존재하는 경우 동기화를 시도하도록 하기 위해 사용될 수 있음</br>

<h3>Samp rate (Sps)</h3>
초당 샘플 수</br>

<h3>Ch0: Center Freq (Hz)</h3>
RF 체인의 전체 주파수</br>
uhd.tune_request(freq, rf_freq = freq - lo_offest, rf_freq_policy=uhd.tune_request.POLICY_MANUAL)</br>
RF 체인에 튜닝 방법을 구현에 지시, IF와 DSP 튜닝에 대한 자동 튜닝 또는 미세한 제어를 선택하는 데 사용</br>

<h3>Ch0: AGC</h3>
Auto Gain Control</br>
세기가 변동하는 전파를 수신할 때 음성 등의 출력이 항상 일정한 크기를 유지하도록 도래전파의 세기에 따라 수신기의 증폭도를 자동으로 변화시키는 것</br>

<h3>Ch0: Gain Value</h3>
0.0 ~ 1.0(1.0은 사용 중인 USRP의 최대 이득에 매핑)</br>
여기서는 0.75</br>

<h3>Ch0: Gain Type</h3>
Normalized(0 to 1)</br>
