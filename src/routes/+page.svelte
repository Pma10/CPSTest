<script>
    let count = 0;
    let time = 0;
    function increaseCount() {
		if (count === 0) {
			startCount();
        }
		count += 1;
    }
  
    function startCount() {
      for (let i = 0; i < 10; i++) {
        setTimeout(() => {
          time += 1;
        }, 1000 * i);
      }
      setTimeout(displayCPS, 10000);
    }
  
    function displayCPS() {
      alert(`당신의 CPS는 ${(count / time).toFixed(1)}입니다`);
	  time = 0
	  count = 0
    }
  </script>
  
  <svelte:head>
    <title>CPS 테스트</title>
    <meta name="description" content="CPS 테스트" />
  </svelte:head>
  
  <body>
    <div>
      <h1>CPS 테스트</h1>
      <div>
        <p>현재 클릭수: {count}</p>
        <p>CPS: {(count / time).toFixed(1)}</p>
        <p>현재 시간 : {time}/10초</p>
      </div>
      <button on:click={increaseCount} id="cpsBtn">
        {count === 0 ? '버튼을 클릭시 시작합니다' : `${count}번`}
      </button>
    </div>
  </body>
  
  <style>
    @font-face {
      font-family: 'Pretendard';
      src: url('https://cdn.jsdelivr.net/gh/Project-Noonnu/noonfonts_2107@1.1/Pretendard-Bold.woff') format('woff');
      font-weight: 900;
      font-style: Bold;
    }
  
    #cpsBtn {
      width: 500px;
      height: 400px; 
	  transition: all 0.25s 0.25s;
	  background-color: rgb(243, 243, 243);
    }
  
	#cpsBtn:hover {
		transform: scale(1.04,1.04);
	}
    body {
      font-family: 'Pretendard';
	  background-color: #dcd9d9;
    }
  
    div {
      text-align: center;
    }
  </style>
  