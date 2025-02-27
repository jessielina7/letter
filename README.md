<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Valentine's Surprise</title>
    <script src="https://code.jquery.com/jquery-3.6.0.min.js"></script>
    <style>
        body {
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            background: url('https://i.pinimg.com/736x/7a/49/ec/7a49ecc5f932a6ed31e82032cb50abb1.jpg') no-repeat center center;
            background-size: cover;
            margin: 0;
        }

        .container {
            position: relative;
        }

        .valentines {
            position: relative;
            top: 50px;
            cursor: pointer;
            animation: up 3s linear infinite;
        }

        @keyframes up {
            0%, 100% {
                transform: translateY(0);
            }
            50% {
                transform: translateY(-30px);
            }
        }

        .envelope {
            position: relative;
            width: 300px;
            height: 200px;
            background-color: #F2E3A3;
            display: flex;
            justify-content: center;
            align-items: center;
        }

        .envelope-text {
            position: absolute;
            top: 50%;
            transform: translateY(-50%);
            font-family: "Copperplate", sans-serif;
            font-size: 22px;
            font-weight: bold;
            color: #000; /* Visible text */
            text-align: center;
            z-index: 20;
            transition: opacity 0.5s ease-in-out;
        }

        .envelope:before {
            background-color: #F2E3A3;
            content: "";
            position: absolute;
            width: 212px;
            height: 212px;
            transform: rotate(45deg);
            top: -105px;
            left: 44px;
            border-radius: 30px 0 0 0;
        }

        .card {
            position: absolute;
            background-color: #f9f9f9;
            width: 270px;
            height: 170px;
            top: 10px;
            left: 15px;
            box-shadow: -5px -5px 100px rgba(0, 0, 0, 0.4);
            display: flex;
            justify-content: center;
            align-items: center;
            flex-direction: column;
            transition: top 0.5s ease-in-out;
        }

        .card:before {
            content: "";
            position: absolute;
            width: 240px;
            height: 140px;
            left: 12px;
            top: 12px;
        }

        .text {
            font-family: "Copperplate";
            font-size: 22px;
            text-align: center;
            color: #003049;
            transition: opacity 0.5s ease-in-out;
        }

        .gif {
            display: none;
            width: 100px;
            margin-top: 10px;
        }

        .front {
            position: absolute;
            border-right: 180px solid #F2E3A3;
            border-top: 95px solid transparent;
            border-bottom: 100px solid transparent;
            left: 120px;
            top: 5px;
            width: 0;
            height: 0;
            z-index: 10;
        }

        .front:before {
            position: absolute;
            content: "";
            border-left: 300px solid #F2E3A3;
            border-top: 195px solid transparent;
            left: -120px;
            top: -95px;
            width: 0;
            height: 0;
        }
    </style>
</head>
<body>
    <div class="container">
        <div class="valentines">
            <div class="envelope">
                <div class="envelope-text">Place your hand here</div>
                <div class="card">
                    <div class="text"></div>
                    <img class="gif" src="https://media3.giphy.com/media/v1.Y2lkPTc5MGI3NjExcTd0ODQ5N21zd2w1bGpkMG5ta3g5dG1oNG45aHRzeGtvOXJ1enV0dyZlcD12MV9pbnRlcm5hbF9naWZfYnlfaWQmY3Q9Zw/MarodU6Pw8pRmvxyyR/giphy.gif" alt="Love GIF">
                </div>
                <div class="front"></div>
            </div>
        </div>
    </div>

    <script>
        $(document).ready(function () {
            $(".container").mouseenter(function () {
                $(".card").stop().animate({ top: "-90px" }, "slow");
                $(".text").text("You are one in a million feeling, I love you! ❤️");
                $(".gif").fadeIn("slow");
                $(".envelope-text").fadeOut("slow"); // Hides text on hover
            });

            $(".container").mouseleave(function () {
                $(".card").stop().animate({ top: "10px" }, "slow");
                $(".text").text("");
                $(".gif").fadeOut("slow");
                $(".envelope-text").fadeIn("slow"); // Shows text again when the cursor leaves
            });
        });
    </script>
</body>
</html>
