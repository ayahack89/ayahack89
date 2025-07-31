# Hi, I'm Ayanabha Chatterjee
## Professional Software Developer | Indie Hacker | Innovator | Freelancer

Being a nerd guy with a deep interest in building things on the internet quickly turned into a focused journey. I started the journey with passion and have now become a professional. I began with frontend development, then moved into backend to understand how everything works behind the scenes. Over time, I learned both and started building multiple full-stack projects. I’ve worked on several innovative ideas that solve real-world problems, always with real users, and I'm still looking for better ideas to build and solve real issues.

Right now, I’m exploring AI not just using tools, but learning how the models actually work and seeking new ideas to implement in the real world. I’m also working on mobile development (at a beginner stage) to expand my skills. I like to experiment, learn by doing, and bring projects to life whether it’s something for work or a side idea I’m passionate about.

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Enhanced Social Media Badges</title>
    <style>
        body {
            margin: 0;
            padding: 40px 20px;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            min-height: 100vh;
            font-family: 'Arial', sans-serif;
            display: flex;
            align-items: center;
            justify-content: center;
        }

        .social-container {
            background: rgba(255, 255, 255, 0.1);
            backdrop-filter: blur(20px);
            border-radius: 30px;
            padding: 40px;
            border: 1px solid rgba(255, 255, 255, 0.2);
            box-shadow: 
                0 20px 40px rgba(0, 0, 0, 0.1),
                inset 0 1px 0 rgba(255, 255, 255, 0.2);
        }

        .badges-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 20px;
            max-width: 800px;
        }

        .badge-link {
            position: relative;
            display: inline-block;
            text-decoration: none;
            transform: translateY(0);
            transition: all 0.4s cubic-bezier(0.175, 0.885, 0.32, 1.275);
        }

        .badge-link:hover {
            transform: translateY(-8px) scale(1.05);
        }

        .badge {
            display: flex;
            align-items: center;
            justify-content: center;
            padding: 12px 24px;
            border-radius: 50px;
            font-weight: 600;
            font-size: 14px;
            color: white;
            position: relative;
            overflow: hidden;
            min-height: 50px;
            box-shadow: 0 8px 25px rgba(0, 0, 0, 0.15);
            transition: all 0.3s ease;
        }

        .badge::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255, 255, 255, 0.3), transparent);
            transition: left 0.6s ease;
        }

        .badge-link:hover .badge::before {
            left: 100%;
        }

        .badge-icon {
            width: 24px;
            height: 24px;
            margin-right: 10px;
            filter: drop-shadow(0 2px 4px rgba(0, 0, 0, 0.2));
        }

        /* Individual badge styles */
        .linkedin {
            background: linear-gradient(135deg, #0077B5, #00A0DC);
            box-shadow: 0 8px 25px rgba(0, 119, 181, 0.3);
        }

        .linkedin:hover {
            background: linear-gradient(135deg, #005885, #0077B5);
            box-shadow: 0 12px 35px rgba(0, 119, 181, 0.4);
        }

        .gmail {
            background: linear-gradient(135deg, #D14836, #EA4335);
            box-shadow: 0 8px 25px rgba(209, 72, 54, 0.3);
        }

        .gmail:hover {
            background: linear-gradient(135deg, #B23121, #D14836);
            box-shadow: 0 12px 35px rgba(209, 72, 54, 0.4);
        }

        .twitter {
            background: linear-gradient(135deg, #1DA1F2, #1991DB);
            box-shadow: 0 8px 25px rgba(29, 161, 242, 0.3);
        }

        .twitter:hover {
            background: linear-gradient(135deg, #0d8bd9, #1DA1F2);
            box-shadow: 0 12px 35px rgba(29, 161, 242, 0.4);
        }

        .youtube {
            background: linear-gradient(135deg, #FF0000, #FF4444);
            box-shadow: 0 8px 25px rgba(255, 0, 0, 0.3);
        }

        .youtube:hover {
            background: linear-gradient(135deg, #CC0000, #FF0000);
            box-shadow: 0 12px 35px rgba(255, 0, 0, 0.4);
        }

        .reddit {
            background: linear-gradient(135deg, #FF4500, #FF6B35);
            box-shadow: 0 8px 25px rgba(255, 69, 0, 0.3);
        }

        .reddit:hover {
            background: linear-gradient(135deg, #E03D00, #FF4500);
            box-shadow: 0 12px 35px rgba(255, 69, 0, 0.4);
        }

        .discord {
            background: linear-gradient(135deg, #5865F2, #7289DA);
            box-shadow: 0 8px 25px rgba(88, 101, 242, 0.3);
        }

        .discord:hover {
            background: linear-gradient(135deg, #4752C4, #5865F2);
            box-shadow: 0 12px 35px rgba(88, 101, 242, 0.4);
        }

        .portfolio {
            background: linear-gradient(135deg, #000000, #333333);
            box-shadow: 0 8px 25px rgba(0, 0, 0, 0.3);
        }

        .portfolio:hover {
            background: linear-gradient(135deg, #111111, #000000);
            box-shadow: 0 12px 35px rgba(0, 0, 0, 0.4);
        }

        /* Floating animation */
        @keyframes float {
            0%, 100% { transform: translateY(0px) rotate(0deg); }
            50% { transform: translateY(-10px) rotate(1deg); }
        }

        .badge-link:nth-child(odd) {
            animation: float 6s ease-in-out infinite;
        }

        .badge-link:nth-child(even) {
            animation: float 6s ease-in-out infinite reverse;
        }

        /* Pulse effect on hover */
        @keyframes pulse {
            0% { box-shadow: 0 0 0 0 rgba(255, 255, 255, 0.4); }
            70% { box-shadow: 0 0 0 20px rgba(255, 255, 255, 0); }
            100% { box-shadow: 0 0 0 0 rgba(255, 255, 255, 0); }
        }

        .badge-link:hover .badge {
            animation: pulse 1.5s infinite;
        }

        /* Responsive design */
        @media (max-width: 768px) {
            .badges-grid {
                grid-template-columns: 1fr;
                gap: 15px;
            }
            
            .social-container {
                padding: 20px;
                margin: 10px;
            }
        }

        /* Glow effect */
        .badge-link::after {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            border-radius: 50px;
            opacity: 0;
            background: radial-gradient(circle, rgba(255, 255, 255, 0.3) 0%, transparent 70%);
            transition: opacity 0.3s ease;
            pointer-events: none;
        }

        .badge-link:hover::after {
            opacity: 1;
        }
    </style>
</head>
<body>
    <div class="social-container">
        <div class="badges-grid">
            <a href="https://linkedin.com/in/ayanabha-chatterjee-104979256" target="_blank" class="badge-link">
                <div class="badge linkedin">
                    <svg class="badge-icon" viewBox="0 0 24 24" fill="white">
                        <path d="M20.447 20.452h-3.554v-5.569c0-1.328-.027-3.037-1.852-3.037-1.853 0-2.136 1.445-2.136 2.939v5.667H9.351V9h3.414v1.561h.046c.477-.9 1.637-1.85 3.37-1.85 3.601 0 4.267 2.37 4.267 5.455v6.286zM5.337 7.433c-1.144 0-2.063-.926-2.063-2.065 0-1.138.92-2.063 2.063-2.063 1.14 0 2.064.925 2.064 2.063 0 1.139-.925 2.065-2.064 2.065zm1.782 13.019H3.555V9h3.564v11.452zM22.225 0H1.771C.792 0 0 .774 0 1.729v20.542C0 23.227.792 24 1.771 24h20.451C23.2 24 24 23.227 24 22.271V1.729C24 .774 23.2 0 22.222 0h.003z"/>
                    </svg>
                    LinkedIn Profile
                </div>
            </a>

            <a href="mailto:ayanabhachatterjee@gmail.com" class="badge-link">
                <div class="badge gmail">
                    <svg class="badge-icon" viewBox="0 0 24 24" fill="white">
                        <path d="M24 5.457v13.909c0 .904-.732 1.636-1.636 1.636h-3.819V11.73L12 16.64l-6.545-4.91v9.273H1.636A1.636 1.636 0 0 1 0 19.366V5.457c0-2.023 2.309-3.178 3.927-1.964L5.455 4.64 12 9.548l6.545-4.91 1.528-1.145C21.69 2.28 24 3.434 24 5.457z"/>
                    </svg>
                    Gmail Contact
                </div>
            </a>

            <a href="https://x.com/ayanabha08" target="_blank" class="badge-link">
                <div class="badge twitter">
                    <svg class="badge-icon" viewBox="0 0 24 24" fill="white">
                        <path d="M18.244 2.25h3.308l-7.227 8.26 8.502 11.24H16.17l-5.214-6.817L4.99 21.75H1.68l7.73-8.835L1.254 2.25H8.08l4.713 6.231zm-1.161 17.52h1.833L7.084 4.126H5.117z"/>
                    </svg>
                    X Follow
                </div>
            </a>

            <a href="https://youtube.com/@MidnightOx8" target="_blank" class="badge-link">
                <div class="badge youtube">
                    <svg class="badge-icon" viewBox="0 0 24 24" fill="white">
                        <path d="M23.498 6.186a3.016 3.016 0 0 0-2.122-2.136C19.505 3.545 12 3.545 12 3.545s-7.505 0-9.377.505A3.017 3.017 0 0 0 .502 6.186C0 8.07 0 12 0 12s0 3.93.502 5.814a3.016 3.016 0 0 0 2.122 2.136c1.871.505 9.376.505 9.376.505s7.505 0 9.377-.505a3.015 3.015 0 0 0 2.122-2.136C24 15.93 24 12 24 12s0-3.93-.502-5.814zM9.545 15.568V8.432L15.818 12l-6.273 3.568z"/>
                    </svg>
                    YouTube Subscribe
                </div>
            </a>

            <a href="https://www.reddit.com/user/Puzzle_Age555" target="_blank" class="badge-link">
                <div class="badge reddit">
                    <svg class="badge-icon" viewBox="0 0 24 24" fill="white">
                        <path d="M12 0A12 12 0 0 0 0 12a12 12 0 0 0 12 12 12 12 0 0 0 12-12A12 12 0 0 0 12 0zm5.01 4.744c.688 0 1.25.561 1.25 1.249a1.25 1.25 0 0 1-2.498.056l-2.597-.547-.8 3.747c1.824.07 3.48.632 4.674 1.488.308-.309.73-.491 1.207-.491.968 0 1.754.786 1.754 1.754 0 .716-.435 1.333-1.01 1.614a3.111 3.111 0 0 1 .042.52c0 2.694-3.13 4.87-7.004 4.87-3.874 0-7.004-2.176-7.004-4.87 0-.183.015-.366.043-.534A1.748 1.748 0 0 1 4.028 12c0-.968.786-1.754 1.754-1.754.463 0 .898.196 1.207.49 1.207-.883 2.878-1.43 4.744-1.487l.885-4.182a.342.342 0 0 1 .14-.197.35.35 0 0 1 .238-.042l2.906.617a1.214 1.214 0 0 1 1.108-.701zM9.25 12C8.561 12 8 12.562 8 13.25c0 .687.561 1.248 1.25 1.248.687 0 1.248-.561 1.248-1.249 0-.688-.561-1.249-1.249-1.249zm5.5 0c-.687 0-1.248.561-1.248 1.25 0 .687.561 1.248 1.249 1.248.688 0 1.249-.561 1.249-1.249 0-.687-.562-1.249-1.25-1.249zm-5.466 3.99a.327.327 0 0 0-.231.094.33.33 0 0 0 0 .463c.842.842 2.484.913 2.961.913.477 0 2.105-.056 2.961-.913a.361.361 0 0 0 .029-.463.33.33 0 0 0-.464 0c-.547.533-1.684.73-2.512.73-.828 0-1.979-.196-2.512-.73a.326.326 0 0 0-.232-.095z"/>
                    </svg>
                    Reddit Join
                </div>
            </a>

            <a href="https://discord.com/users/1340353196245127270" target="_blank" class="badge-link">
                <div class="badge discord">
                    <svg class="badge-icon" viewBox="0 0 24 24" fill="white">
                        <path d="M20.317 4.3698a19.7913 19.7913 0 00-4.8851-1.5152.0741.0741 0 00-.0785.0371c-.211.3753-.4447.8648-.6083 1.2495-1.8447-.2762-3.68-.2762-5.4868 0-.1636-.3933-.4058-.8742-.6177-1.2495a.077.077 0 00-.0785-.037 19.7363 19.7363 0 00-4.8852 1.515.0699.0699 0 00-.0321.0277C.5334 9.0458-.319 13.5799.0992 18.0578a.0824.0824 0 00.0312.0561c2.0528 1.5076 4.0413 2.4228 5.9929 3.0294a.0777.0777 0 00.0842-.0276c.4616-.6304.8731-1.2952 1.226-1.9942a.076.076 0 00-.0416-.1057c-.6528-.2476-1.2743-.5495-1.8722-.8923a.077.077 0 01-.0076-.1277c.1258-.0943.2517-.1923.3718-.2914a.0743.0743 0 01.0776-.0105c3.9278 1.7933 8.18 1.7933 12.0614 0a.0739.0739 0 01.0785.0095c.1202.099.246.1981.3728.2924a.077.077 0 01-.0066.1276 12.2986 12.2986 0 01-1.873.8914.0766.0766 0 00-.0407.1067c.3604.698.7719 1.3628 1.225 1.9932a.076.076 0 00.0842.0286c1.961-.6067 3.9495-1.5219 6.0023-3.0294a.077.077 0 00.0313-.0552c.5004-5.177-.8382-9.6739-3.5485-13.6604a.061.061 0 00-.0312-.0286zM8.02 15.3312c-1.1825 0-2.1569-1.0857-2.1569-2.419 0-1.3332.9555-2.4189 2.157-2.4189 1.2108 0 2.1757 1.0952 2.1568 2.419-.0189 1.3332-.9555 2.4189-2.1569 2.4189zm7.9748 0c-1.1825 0-2.1569-1.0857-2.1569-2.419 0-1.3332.9554-2.4189 2.1569-2.4189 1.2108 0 2.1757 1.0952 2.1568 2.419 0 1.3332-.9555 2.4189-2.1568 2.4189Z"/>
                    </svg>
                    Discord Chat
                </div>
            </a>

            <a href="https://portfolio-ayanabha.vercel.app" target="_blank" class="badge-link">
                <div class="badge portfolio">
                    <svg class="badge-icon" viewBox="0 0 24 24" fill="white">
                        <path d="M12 2L2 7l10 5 10-5-10-5zM2 17l10 5 10-5M2 12l10 5 10-5"/>
                    </svg>
                    Portfolio Visit
                </div>
            </a>
        </div>
    </div>
</body>
</html>



**You can explore one of the top projects pinned in my profile below or even contribute to my [open-source GitHub repository](http://www.github.com/ayahack89/termino). I’m also running a VS Code extension, **Termino**, which you can install directly from the [Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=ayanabhachatterjee.termino). It already has real users, so give it a try and help me make it even better!**


## Active on x(twitter) to collaborate, hit me up with a dm!  
For professional proposals and freelancing requests, email me at **ayanabhachatterjee@gmail.com**

___

<div align="center">
  <em>Build in silence, engage in public.</em>
</div>
