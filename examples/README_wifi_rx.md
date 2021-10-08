<h1>wifi_rx</h1>
<h2>UHD: USRP Source</h2>
USRP 장치에서 샘플을 스트리밍하는 데 사용(수신기 역할)</br>
스로틀 역할</br>
(Throttle:평균 속도가 특정 속도를 초과하지 않도록 샘플의 스로틀 흐름)</br>

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
</br>

<h2>Complex to Mag^2</h2>
입력의 크기를 계산하고 제곱, 벡터에서도 작동</br>
</br>

<h2>Moving Average</h2>
입력의 이동 평균 계산</br>
Output[i] = scale * sum(input[i-length: i])</br>

<h3>Length</h3>
사용할 이동 평균 window의 크기</br>
window_size + 16으로 설정</br>

<h3>Scale</h3>
마지막 sample의 합계를 척도화하는 요인</br>
실제 이동 평균을 얻으려면 1/Length로 설정</br>
여기서는 1로 설정</br>

<h3>Max Iter</h3>
블록이 작업 함수의 한 호출에서 처리할 최대 샘플 수</br>
</br>

<h2>Delay</h2>
일정 수의 샘플로 입력을 지연</br>
</br>

<h2>Complex Conjugate</h2>
출력은 입력의 복잡한 결합</br>
</br>

<h2>Multiply</h2>
모든 input stream을 곱함</br>
</br>

<h2>Complex to Mag</h2>
복합 sample의 크기를 계산, 벡터에서도 작동</br>
</br>

<h2>Divide</h2>
모든 input stream을 나눔</br>
output = input[0] / input[1] / ... / input[M-1]</br>
</br>

<h2>QT GUI Time Sink</h2>
여러 신호를 시간 내에 표시하기 위한 그래픽 sink</br>
</br>

<h2>Stream to Vector</h2>
stream of items를 Num Items를 포함하는 vector stream으로 변환</br>
</br>

<h2>FFT</h2>
float나 complex value의 벡터를 취하여 FFT를 계산</br>

<h3>FFT Size</h3>
각 FFT 계산에 사용된 샘플의 수, 출력에 있는 점의 개수도 결정</br>

<h3>Forward/Reverse</h3>
FFT와 IFFT의 여부</br>

<h3>Window</h3>
FFT를 사용하기 전에 각 sample 세트에 적용할 window type</br>

<h3>Shift</h3>
DC(0Hz)를 중심에 놓는 "ft shift"를 할 것인지 여부</br>

<h3>Num. Threads</h3>
FFT 수행에 할당할 스레드 수</br>
</br>

<h2>PDU to Tagged Stream</h2>
수신된 PDU를 태그가 지정된 항목 스트림으로 변환</br>

<h3>Length tag name</h3>
패킷의 길이를 지정하는 태그의 이름</br>
</br>

<h2>QT GUI Constellation Sink</h2>
여러 신호의 IQ 별자리를 표시하는 그래픽 sink</br>
</br>

<h2>File Sink</h2>
이진 파일에 스트림을 쓰는 데 사용</br>

<h3>File</h3>
열고 출력을 작성할 파일의 이름</br>

<h3>Unbuffered</h3>
출력을 메모리에서 버퍼링할지 여부</br>

<h3>Append file</h3>
파일에 추가할지 또는 매번 새 파일을 작성할지 여부</br>
</br>
