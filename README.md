# De-il-bilekler-
<!DOCTYPE html>  <html lang="tr">  
<head>  
    <meta charset="UTF-8">  
    <meta name="viewport" content="width=device-width, initial-scale=1.0">  
    <title>Benimle Çıkar Mısın?</title>  
    <style>  
        * {  
            box-sizing: border-box;  
            margin: 0;  
            padding: 0;  
        }  body {  
        font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;  
        /* Kalpli kırmızı arka plan */  
        background-color: #d32f2f;  
        background-image: url('https://images.unsplash.com/photo-1518199266791-5375a83190b7?q=80&w=1000&auto=format&fit=crop');  
        background-size: cover;  
        background-position: center;  
        height: 100vh;  
        display: flex;  
        justify-content: center;  
        align-items: center;  
        overflow: hidden;  
        position: relative;  
    }  

    /* Köşelerdeki Güller */  
    .rose {  
        position: absolute;  
        width: 150px;  
        height: 150px;  
        background-image: url('https://cdn-icons-png.flaticon.com/512/3468/3468380.png');  
        background-size: contain;  
        background-repeat: no-repeat;  
        z-index: 10;  
        pointer-events: none;  
    }  
    .top-left { top: 10px; left: 10px; transform: rotate(-45deg); }  
    .top-right { top: 10px; right: 10px; transform: rotate(45deg); }  
    .bottom-left { bottom: 10px; left: 10px; transform: rotate(-135deg); }  
    .bottom-right { bottom: 10px; right: 10px; transform: rotate(135deg); }  

    /* Ana Kart */  
    .container {  
        text-align: center;  
        background: rgba(255, 255, 255, 0.9);  
        padding: 40px;  
        border-radius: 20px;  
        box-shadow: 0 10px 30px rgba(0,0,0,0.3);  
        max-width: 90%;  
        width: 450px;  
        z-index: 5;  
        transition: all 0.3s ease;  
    }  

    h1 {  
        color: #b71c1c;  
        margin-bottom: 30px;  
        font-size: 2rem;  
    }  

    .buttons {  
        display: flex;  
        justify-content: center;  
        align-items: center;  
        gap: 20px;  
        flex-wrap: wrap;  
    }  

    button {  
        padding: 12px 30px;  
        font-size: 1.2rem;  
        font-weight: bold;  
        border: none;  
        border-radius: 50px;  
        cursor: pointer;  
        transition: transform 0.1s ease;  
        box-shadow: 0 4px 15px rgba(0,0,0,0.2);  
    }  

    /* İstediğin Renk Ayarları */  
    #yesBtn {  
        background-color: #2e7d32; /* Yeşil */  
        color: white;  
        z-index: 100;  
    }  

    #noBtn {  
        background-color: #c62828; /* Kırmızı */  
        color: white;  
    }  

    /* Sonuç Ekranı (Kedi ve Yazı) */  
    .result-screen {  
        display: none;  
        position: fixed;  
        top: 0;  
        left: 0;  
        width: 100vw;  
        height: 100vh;  
        background-color: #ffdde1;  
        background-image: linear-gradient(to top, #ff9a9e 0%, #fecfef 99%, #fecfef 100%);  
        flex-direction: column;  
        justify-content: center;  
        align-items: center;  
        z-index: 200;  
        text-align: center;  
    }  

    .result-screen h2 {  
        color: #b71c1c;  
        font-size: 2.5rem;  
        margin-bottom: 20px;  
        padding: 0 20px;  
    }  

    /* Gül Tutan Kedi Görseli */  
    .cat-img {  
        width: 300px;  
        max-width: 80%;  
        border-radius: 20px;  
        box-shadow: 0 10px 25px rgba(0,0,0,0.2);  
    }  

    /* Mobil Ekranlar İçin Gül Boyutu Ayarı */  
    @media (max-width: 600px) {  
        .rose { width: 80px; height: 80px; }  
    }  
</style>

</head>  
<body>  <div class="rose top-left"></div>  
<div class="rose top-right"></div>  
<div class="rose bottom-left"></div>  
<div class="rose bottom-right"></div>  

<div class="container" id="mainContainer">  
    <h1>Benimle Çıkar mısın?</h1>  
    <div class="buttons">  
        <button id="yesBtn" onclick="selectYes()">Evet</button>  
        <button id="noBtn" onclick="growYes()">Hayır</button>  
    </div>  
</div>  

<div class="result-screen" id="resultScreen">  
    <h2>Evet diyeceğini biliyordum! ❤️</h2>  
    <img class="cat-img" src="https://images.unsplash.com/photo-1514888286974-6c03e2ca1dba?q=80&w=1000&auto=format&fit=crop" alt="Mutlu Kedi">  
</div>  

<script>  
    let scale = 1;  
    const yesButton = document.getElementById('yesBtn');  
    const noButton = document.getElementById('noBtn');  

    function growYes() {  
        // Hayır'a her tıklandığında Evet butonunu büyütür  
        scale += 0.4;  
        yesButton.style.transform = `scale(${scale})`;  
          
        // Eğer Evet butonu ekranın çoğunu kaplayacak kadar büyürse otomatik kabul et  
        if (scale > 5) {  
            selectYes();  
        }  
    }  

    function selectYes() {  
        // Sonuç ekranını gösterir  
        document.getElementById('resultScreen').style.display = 'flex';  
    }  
</script>

</body>  
</html>  
