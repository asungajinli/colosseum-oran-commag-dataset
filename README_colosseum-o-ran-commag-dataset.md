# Colosseum O-RAN COMMAG Dataset
This repository contains the dataset for the paper L. Bonati, S. D'Oro, M. Polese, S. Basagni, T. Melodia, "Intelligence and Learning in O-RAN for Data-driven NextG Cellular Networks," IEEE Communications Magazine, vol. 59, no. 10, pp. 21–27, October 2021. Please cite the paper if you plan to use it in your publication.

## Experiment setup
- Number of Base Stations (BSs): 4
- Channel bandwidth: 3 MHz (15 Physical Resource Blocks (PRBs))
- Number of slices for each BS: 3
- Scheduling policies available to each slice:
	- Policy 0: Round-robin (RR)
  	- Policy 1: Waterfilling (WF)
  	- Policy 2: Proportionally fair (PF)
- Number of User Equipments (UEs): 40
- Radio Frequency (RF) scenario setup (Colosseum Rome scenario):
  	- Close: UEs uniformly distributed within 20 m of each BS
  	- Medium: UEs uniformly distributed within 50 m of each BS
  	- Far: UEs uniformly distributed within 100 m of each BS
- UE Mobility:
  	- Static: no mobility
  	- Slow: 3 m/s
- Traffic classes:
  	- eMBB: Constant bitrate traffic (1 Mbps per UE)
  	- MTC: Poisson traffic (30 pkt/s of 125 bytes per UE)
  	- URLLC: Poisson traffic (10 pkt/s of 125 bytes per UE)
- UEs belong to different traffic classes:
  	- eMBB UEs: 2, 5, 8, 12, 15, 18, 22, 25, 28, 32, 35, 38
  	- MTC UEs: 3, 6, 9, 13, 16, 19, 23, 26, 29, 33, 36, 39
  	- URLLC UEs: 1, 4, 7, 10, 11, 14, 17, 20, 21, 24, 27, 30, 31, 34, 37, 40

## Dataset structure
- ``slice_mixed``: UEs are randomly distributed across slices
- ``slice_traffic``: UEs are divided per slice based on traffic types:
  	- Slice 0: eMBB UEs
  	- Slice 1: MTC UEs
  	- Slice 2: URLLC UEs

## Training configurations
The scheduling policies and initial Resource Block Group (RBG) allocations for each slice are as follows.

<table>
<thead>
<tr>
<th></th>
<th align="center" colspan="3">Slice Scheduling Policy</th>
<th align="center" colspan="3">Slice RBG Allocation</th>
</tr>
</thead>
<thead>
<tr>
<th align="center">Training</th>
<th align="center">Slice 0</th>
<th align="center">Slice 1</th>
<th align="center">Slice 2</th>
<th align="center">Slice 0</th>
<th align="center">Slice 1</th>
<th align="center">Slice 2</th>
</tr>
</thead>
<tbody>
<tr>
<td align="right">tr0</td>
<td align="right">PF</td>
<td align="right">RR</td>
<td align="right">PF</td>
<td align="right">1</td>
<td align="right">2</td>
<td align="right">4</td>
</tr>
<tr>
<td align="right">tr1</td>
<td align="right">WF</td>
<td align="right">RR</td>
<td align="right">RR</td>
<td align="right">1</td>
<td align="right">4</td>
<td align="right">2</td>
</tr>
<tr>
<td align="right">tr2</td>
<td align="right">RR</td>
<td align="right">PF</td>
<td align="right">WF</td>
<td align="right">2</td>
<td align="right">1</td>
<td align="right">4</td>
</tr>
<tr>
<td align="right">tr3</td>
<td align="right">WF</td>
<td align="right">WF</td>
<td align="right">PF</td>
<td align="right">2</td>
<td align="right">4</td>
<td align="right">1</td>
</tr>
<tr>
<td align="right">tr4</td>
<td align="right">RR</td>
<td align="right">WF</td>
<td align="right">WF</td>
<td align="right">4</td>
<td align="right">2</td>
<td align="right">1</td>
</tr>
<tr>
<td align="right">tr5</td>
<td align="right">WF</td>
<td align="right">WF</td>
<td align="right">WF</td>
<td align="right">4</td>
<td align="right">1</td>
<td align="right">2</td>
</tr>
<tr>
<td align="right">tr6</td>
<td align="right">PF</td>
<td align="right">PF</td>
<td align="right">WF</td>
<td align="right">2</td>
<td align="right">2</td>
<td align="right">3</td>
</tr>
<tr>
<td align="right">tr7</td>
<td align="right">WF</td>
<td align="right">RR</td>
<td align="right">PF</td>
<td align="right">2</td>
<td align="right">3</td>
<td align="right">2</td>
</tr>
<tr>
<td align="right">tr8</td>
<td align="right">WF</td>
<td align="right">PF</td>
<td align="right">RR</td>
<td align="right">3</td>
<td align="right">2</td>
<td align="right">2</td>
</tr>
<tr>
<td align="right">tr9</td>
<td align="right">PF</td>
<td align="right">WF</td>
<td align="right">RR</td>
<td align="right">3</td>
<td align="right">3</td>
<td align="right">1</td>
</tr>
<tr>
<td align="right">tr10</td>
<td align="right">RR</td>
<td align="right">RR</td>
<td align="right">PF</td>
<td align="right">3</td>
<td align="right">1</td>
<td align="right">3</td>
</tr>
<tr>
<td align="right">tr11</td>
<td align="right">RR</td>
<td align="right">PF</td>
<td align="right">RR</td>
<td align="right">1</td>
<td align="right">3</td>
<td align="right">3</td>
</tr>
<tr>
<td align="right">tr12</td>
<td align="right">RR</td>
<td align="right">RR</td>
<td align="right">RR</td>
<td align="right">1</td>
<td align="right">2</td>
<td align="right">4</td>
</tr>
<tr>
<td align="right">tr13</td>
<td align="right">WF</td>
<td align="right">PF</td>
<td align="right">WF</td>
<td align="right">1</td>
<td align="right">4</td>
<td align="right">2</td>
</tr>
<tr>
<td align="right">tr14</td>
<td align="right">PF</td>
<td align="right">WF</td>
<td align="right">PF</td>
<td align="right">4</td>
<td align="right">2</td>
<td align="right">1</td>
</tr>
<tr>
<td align="right">tr15</td>
<td align="right">RR</td>
<td align="right">WF</td>
<td align="right">PF</td>
<td align="right">3</td>
<td align="right">1</td>
<td align="right">4</td>
</tr>
<tr>
<td align="right">tr16</td>
<td align="right">PF</td>
<td align="right">RR</td>
<td align="right">RR</td>
<td align="right">1</td>
<td align="right">2</td>
<td align="right">4</td>
</tr>
<tr>
<td align="right">tr17</td>
<td align="right">PF</td>
<td align="right">RR</td>
<td align="right">WF</td>
<td align="right">1</td>
<td align="right">2</td>
<td align="right">4</td>
</tr>
</tbody>
</table>

## Dynamic slice resizing
After the initial allocation, the RBGs for each slice are dynamically re-allocated as follows.

<table>
<thead>
<tr>
<th align="center">Time [s]</th>
<th align="center">RBG Slice 0</th>
<th align="center">RBG Slice 1</th>
<th align="center">RBG Slice 2</th>
</tr>
</thead>
<tbody>
<tr>
<td align="right">0-30</td>
  <td align="center" colspan="3">initial allocation (see training configurations above)</td>
</tr>
<tr>
<td align="right">30-60</td>
<td align="right">1</td>
<td align="right">2</td>
<td align="right">4</td>
</tr>
<tr>
<td align="right">60-90</td>
<td align="right">1</td>
<td align="right">4</td>
<td align="right">2</td>
</tr>
<tr>
<td align="right">90-120</td>
<td align="right">2</td>
<td align="right">1</td>
<td align="right">4</td>
</tr>
<tr>
<td align="right">120-150</td>
<td align="right">2</td>
<td align="right">4</td>
<td align="right">1</td>
</tr>
<tr>
<td align="right">150-180</td>
<td align="right">4</td>
<td align="right">2</td>
<td align="right">1</td>
</tr>
<tr>
<td align="right">180-210</td>
<td align="right">4</td>
<td align="right">1</td>
<td align="right">2</td>
</tr>
<tr>
<td align="right">210-240</td>
<td align="right">2</td>
<td align="right">2</td>
<td align="right">3</td>
</tr>
<tr>
<td align="right">240-270</td>
<td align="right">2</td>
<td align="right">3</td>
<td align="right">2</td>
</tr>
<tr>
<td align="right">270-300</td>
<td align="right">3</td>
<td align="right">2</td>
<td align="right">2</td>
</tr>
<tr>
<td align="right">300-330</td>
<td align="right">3</td>
<td align="right">3</td>
<td align="right">1</td>
</tr>
<tr>
<td align="right">330-360</td>
<td align="right">3</td>
<td align="right">1</td>
<td align="right">3</td>
</tr>
<tr>
<td align="right">360-390</td>
<td align="right">1</td>
<td align="right">3</td>
<td align="right">3</td>
</tr>
<tr>
<td align="right">390-420</td>
<td align="right">1</td>
<td align="right">2</td>
<td align="right">4</td>
</tr>
<tr>
<td align="right">420-450</td>
<td align="right">1</td>
<td align="right">4</td>
<td align="right">2</td>
</tr>
<tr>
<td align="right">450-480</td>
<td align="right">4</td>
<td align="right">2</td>
<td align="right">1</td>
</tr>
</tbody>
</table>


## Testing the DRL agents
This repository contains the script ``test_agent_release.py``, which is used to test the DRL agents we used in our work. The script executes in three phases:
- Phase 1: loading agents and encoder from ``ml_models``;
- Phase 2: loading data from the CSV files in the repository;
- Phase 3: feeding the DRL agents which compute the best action for the current state. This phase runs in a loop.

All required dependencies are included in the ``requirements.txt`` file.

Remark 1: anyone interested in feeding real-time data to the DRL agents must implement proper methods to (i) gather data from DUs (i.e., ``get_data_from_DUs()``);  (ii) feed it to the DRL agent (i.e., ``split_data()``); and (iii) feed back the output of the DRL agent to the DUs (i.e., ``send_action_to_DU()``). 

---
### Phase 1
We load the 3 DRL agents and the encoder portion of the autoencoder we used in the experimental section of our work. All models are stored in ``ml_models`` and loaded when starting the script. We have one DRL agent (i.e., the trained Proximal Policy Optimization (PPO) policy network) per slice. Rewards vary across the various DRL agents and are set as follows:
- eMBB slice: Maximize throughput. This is done by setting the reward equal to ``tx_brate downlink [Mbps]``, which represents the downlink throughput in Mbps as measured by srsLTE;
- MTC slice: Maximize throughput. This is done by setting the reward equal to ``tx_brate downlink [Mbps]``, which represents the downlink throughput in Mbps as measured by srsLTE;
- URLLC slice: Minimize latency. This is done by setting the reward equal to ``ratio_granted_req``, which represents the ratio between the number of PRBs allocated by the scheduler and those requested by the UEs. The higher the value, the faster requests are satisfied and traffic experience low latency.

These metrics are reported periodically by DUs and, in our case, are contained in the CSV repository included in this repository.

### Phase 2
We load the CSV dataset included in the repository. CSV files are loaded into Pandas DataFrame structures, which are used in this case to feed the DRL agents with data. In real-world deployments, data is reported directly from DUs. In this case, and for testing purposes only, we provide functions to emulate such data by extracting it from the dataset we collected.

### Phase 3
We run a loop that extracts data from the dataset and feeds it to each DRL agent. Data is taken from the dataset at random, grouped according to the slice they belong to, and fed to the corresponding DRL agent, which uses the PPO policy network to compute the best action to maximize the reward.

### Phase 1
우리는 실험 섹션에서 사용한 오토인코더의 인코더 부분과 3 개의 DRL 에이전트를 로드합니다. 모든 모델은 ml_models에 저장되어 있으며 스크립트를 시작할 때 로드됩니다. 슬라이스 당 하나의 DRL 에이전트 (즉, 훈련 된 Proximal Policy Optimization (PPO) 정책 네트워크)가 있습니다. 보상은 다양한 DRL 에이전트 간에 다르며 다음과 같이 설정됩니다.

- eMBB 슬라이스 : 처리량을 최대화합니다. 이것은 tx_brate downlink [Mbps]를 보상으로 설정하여 srsLTE에 의해 측정 된 Mbps로 나타낸 다운 링크 처리량을 나타냅니다.
- MTC 슬라이스 : 처리량을 최대화합니다. 이것은 tx_brate downlink [Mbps]를 보상으로 설정하여 srsLTE에 의해 측정 된 Mbps로 나타낸 다운 링크 처리량을 나타냅니다.
- URLLC 슬라이스 : 지연 시간을 최소화합니다. 이것은 스케줄러에 의해 할당 된 PRB 수와 UE가 요청 한 PRB 수 사이의 비율인 ratio_granted_req를 보상으로 설정하여 요청이 더 빨리 충족되고 트래픽이 낮은 지연 시간을 경험할 수 있습니다. 이러한 메트릭은 DUs에서 주기적으로보고되며 우리의 경우 이 저장소에 포함 된 CSV 저장소에 포함됩니다.

### Phase 2
저장소에 포함 된 CSV 데이터 세트를 로드합니다. CSV 파일은 Pandas DataFrame 구조로 로드되며 이 경우 DRL 에이전트에 데이터를 공급하는 데 사용됩니다. 실제 세계 배치에서 데이터는 DUs에서 직접보고됩니다. 이 경우 테스트 목적으로만 데이터를 에뮬레이트하기 위해 수집 한 데이터 세트에서 추출하는 함수를 제공합니다.

### Phase 3
데이터 세트에서 데이터를 추출하고 각 DRL 에이전트에 공급하는 루프를 실행합니다. 데이터는 임의로 추출되며 소속되는 슬라이스에 따라 그룹화되어 해당 DRL 에이전트에 공급됩니다. 해당 DRL 에이전트는 PPO 정책 네트워크를 사용하여 보상을 최대화하는 최상의 작업을 계산합니다.