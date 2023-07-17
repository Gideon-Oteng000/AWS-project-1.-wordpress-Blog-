# HOW I HOSTED MY WORDPRESS BLOG ON AWS [DEONCLOUD.COM](https://deoncloud.com "Deoncloud blog")
--- 

## ALL THE AWS SERVICES USED 
- ![EC2 ICON](<svg class="w-4 h-4" height="40" width="40" xmlns="http://www.w3.org/2000/svg"><defs><linearGradient x1="0%" y1="100%" x2="100%" y2="0%" id="Arch_Amazon-EC2_32_svg__a"><stop stop-color="#C8511B" offset="0%"></stop><stop stop-color="#F90" offset="100%"></stop></linearGradient></defs><g fill="none" fill-rule="evenodd"><path d="M0 0h40v40H0z" fill="url(#Arch_Amazon-EC2_32_svg__a)"></path><path d="M26.052 27L26 13.948 13 14v13.052L26.052 27zM27 14h2v1h-2v2h2v1h-2v2h2v1h-2v2h2v1h-2v2h2v1h-2v.052a.95.95 0 01-.948.948H26v2h-1v-2h-2v2h-1v-2h-2v2h-1v-2h-2v2h-1v-2h-2v2h-1v-2h-.052a.95.95 0 01-.948-.948V27h-2v-1h2v-2h-2v-1h2v-2h-2v-1h2v-2h-2v-1h2v-2h-2v-1h2v-.052a.95.95 0 01.948-.948H13v-2h1v2h2v-2h1v2h2v-2h1v2h2v-2h1v2h2v-2h1v2h.052a.95.95 0 01.948.948V14zm-6 19H7V19h2v-1H7.062C6.477 18 6 18.477 6 19.062v13.876C6 33.523 6.477 34 7.062 34h13.877c.585 0 1.061-.477 1.061-1.062V31h-1v2zM34 7.062v13.876c0 .585-.476 1.062-1.061 1.062H30v-1h3V7H19v3h-1V7.062C18 6.477 18.477 6 19.062 6h13.877C33.524 6 34 6.477 34 7.062z" fill="#FFF"></path></g></svg>) EC2 (Virtual Server)
- <svg class="w-6 h-6" height="40" width="40" xmlns="http://www.w3.org/2000/svg"><defs><linearGradient x1="0%" y1="100%" x2="100%" y2="0%" id="Arch_Amazon-Route-53_32_svg__a"><stop stop-color="#4D27A8" offset="0%"></stop><stop stop-color="#A166FF" offset="100%"></stop></linearGradient></defs><g fill="none" fill-rule="evenodd"><path d="M0 0h40v40H0z" fill="url(#Arch_Amazon-Route-53_32_svg__a)"></path><path d="M24.024 20.314c.343.317.514.74.514 1.272 0 .58-.208 1.042-.624 1.388-.416.345-.977.518-1.68.518a4.112 4.112 0 01-1.647-.354v-.71c.643.214 1.193.32 1.648.32.448 0 .794-.101 1.036-.302.242-.2.363-.488.363-.86 0-.715-.452-1.072-1.355-1.072a8.13 8.13 0 00-.842.044v-.585l1.86-2.03h-2.622v-.726h3.607v.7l-1.826 1.932a.447.447 0 01.089-.009h.088c.584 0 1.048.159 1.391.474m-5.147-.154c.359.336.54.8.54 1.39 0 .58-.21 1.049-.63 1.405-.42.358-.972.537-1.656.537a4.09 4.09 0 01-1.692-.354v-.71c.655.214 1.216.32 1.683.32.448 0 .793-.102 1.032-.306.239-.204.36-.498.36-.882 0-.42-.113-.725-.338-.913-.224-.189-.59-.284-1.099-.284-.366 0-.823.03-1.373.09v-.587l.169-2.65h3.233v.727h-2.489l-.116 1.8c.326-.06.618-.09.878-.09.638 0 1.138.17 1.498.507m6.653 6.462c-2.242.403-4.207 1.313-5.53 2.059-1.323-.746-3.288-1.656-5.53-2.06-.627-.112-3.755-.764-3.755-2.558 0-.836.301-1.392.877-2.385.696-1.2 1.562-2.693 1.562-4.848 0-1.528-.399-2.996-1.187-4.368l.25-.306c2.61 1.293 5.533 1.118 7.783-.304 2.25 1.421 5.173 1.597 7.783.304l.25.306c-.788 1.372-1.188 2.84-1.188 4.368 0 2.155.866 3.648 1.563 4.848.576.993.876 1.549.876 2.385 0 1.794-3.127 2.446-3.754 2.559m2.312-9.792c0-1.454.41-2.849 1.22-4.146a.502.502 0 00-.036-.58l-.726-.893a.497.497 0 00-.63-.123c-1.134.627-2.319.945-3.518.945-1.448 0-2.714-.39-3.868-1.19a.502.502 0 00-.568 0c-1.155.8-2.42 1.19-3.868 1.19-1.2 0-2.384-.318-3.52-.945a.495.495 0 00-.628.123l-.726.893a.5.5 0 00-.036.58c.809 1.297 1.219 2.692 1.219 4.146 0 1.887-.791 3.25-1.428 4.347-.626 1.08-1.011 1.798-1.011 2.886 0 2.524 3.502 3.348 4.575 3.54 2.246.404 4.207 1.356 5.456 2.084a.493.493 0 00.502 0c1.25-.728 3.21-1.68 5.455-2.083 1.074-.193 4.575-1.017 4.575-3.541 0-1.088-.384-1.806-1.01-2.886-.637-1.096-1.429-2.46-1.429-4.347M26.01 29.297c-2.822.507-5.19 2.016-6.01 2.588-.82-.572-3.188-2.08-6.01-2.588-1.406-.252-5.992-1.376-5.992-5.234 0-1.606.631-2.696 1.244-3.75.587-1.013 1.195-2.06 1.195-3.483 0-2.217-1.265-3.791-1.913-4.452.676-.821 2.314-2.818 3.147-3.89 1.263 1.18 2.728 1.824 4.177 1.824 1.61 0 2.942-.65 4.152-2.036 1.21 1.387 2.543 2.036 4.152 2.036 1.449 0 2.914-.643 4.176-1.824.833 1.072 2.472 3.069 3.148 3.89-.649.66-1.913 2.235-1.913 4.452 0 1.423.608 2.47 1.195 3.483.612 1.054 1.244 2.144 1.244 3.75 0 3.858-4.587 4.982-5.992 5.234m5.611-9.485c-.57-.98-1.06-1.828-1.06-2.982 0-2.43 1.892-4.004 1.912-4.02a.503.503 0 00.07-.705c-.03-.037-3.066-3.716-3.759-4.668a.497.497 0 00-.768-.047c-1.16 1.24-2.532 1.924-3.864 1.924-1.471 0-2.63-.656-3.756-2.128a.516.516 0 00-.793 0c-1.126 1.472-2.285 2.128-3.755 2.128-1.332 0-2.704-.683-3.864-1.924a.497.497 0 00-.768.047c-.693.952-3.728 4.63-3.76 4.668a.502.502 0 00.072.705c.019.016 1.911 1.575 1.911 4.02 0 1.154-.49 2.001-1.061 2.982C7.732 20.926 7 22.188 7 24.062c0 3.127 2.546 5.451 6.813 6.217 3.19.574 5.857 2.597 5.883 2.617a.499.499 0 00.608 0c.026-.02 2.694-2.043 5.883-2.617C30.453 29.513 33 27.19 33 24.063c0-1.875-.732-3.137-1.379-4.25" fill="#FFF"></path></g></svg> ROUTE 53 (DNS Web Services)
- <svg class="w-6 h-6" height="40" width="40" xmlns="http://www.w3.org/2000/svg"><defs><linearGradient x1="0%" y1="100%" x2="100%" y2="0%" id="Arch_Elastic-Load-Balancing_32_svg__a"><stop stop-color="#4D27A8" offset="0%"></stop><stop stop-color="#A166FF" offset="100%"></stop></linearGradient></defs><g fill="none" fill-rule="evenodd"><path d="M0 0h40v40H0z" fill="url(#Arch_Elastic-Load-Balancing_32_svg__a)"></path><path d="M15 27c-3.859 0-7-3.14-7-7s3.141-7 7-7 7 3.14 7 7-3.141 7-7 7m14 1c1.103 0 2 .897 2 2s-.897 2-2 2-2-.897-2-2 .897-2 2-2m0-20c1.103 0 2 .897 2 2s-.897 2-2 2-2-.897-2-2 .897-2 2-2m1 10.5c1.103 0 2 .897 2 2s-.897 2-2 2-2-.897-2-2 .897-2 2-2M22.931 21h4.12A2.997 2.997 0 0030 23.5c1.654 0 3-1.346 3-3s-1.346-3-3-3a2.997 2.997 0 00-2.949 2.5H23c0-1.489-.416-2.88-1.128-4.075l4.827-4.023A2.982 2.982 0 0029 13c1.654 0 3-1.346 3-3s-1.346-3-3-3-3 1.346-3 3c0 .361.074.702.191 1.022l-4.885 4.072A7.985 7.985 0 0015 12c-4.411 0-8 3.589-8 8s3.589 8 8 8a7.985 7.985 0 006.306-3.094l4.885 4.072c-.117.32-.191.661-.191 1.022 0 1.654 1.346 3 3 3s3-1.346 3-3-1.346-3-3-3c-.929 0-1.75.433-2.301 1.098l-4.827-4.023A7.927 7.927 0 0022.931 21" fill="#FFF"></path></g></svg> Application Load Balancer (traffic load balancing)
- <svg class="w-6 h-6" height="40" width="40" xmlns="http://www.w3.org/2000/svg"><defs><linearGradient x1="0%" y1="100%" x2="100%" y2="0%" id="Arch_Amazon-EC2-Auto-Scaling_32_svg__a"><stop stop-color="#C8511B" offset="0%"></stop><stop stop-color="#F90" offset="100%"></stop></linearGradient></defs><g fill="none" fill-rule="evenodd"><path d="M0 0h40v40H0z" fill="url(#Arch_Amazon-EC2-Auto-Scaling_32_svg__a)"></path><path d="M24 17.962v-1.524a.505.505 0 00-.5-.508h-7c-.275 0-.5.227-.5.508v7.113c0 .28.225.508.5.508h7c.275 0 .5-.227.5-.508v-5.589zm1-3.049h1v1.017h-1.092c.056.16.092.329.092.508v1.524h1v1.016h-1v2.033h1v1.016h-1v1.524c0 .179-.036.349-.092.508H26v1.017h-1v1.016h-1v-1.11a1.462 1.462 0 01-.5.094H22v1.016h-1v-1.016h-2v1.016h-1v-1.016h-1.5c-.176 0-.343-.037-.5-.094v1.11h-1v-1.016h-1v-1.017h1.092a1.529 1.529 0 01-.092-.508v-1.524h-1V21.01h1v-2.033h-1v-1.016h1v-1.524c0-.18.036-.349.092-.508H14v-1.017h1v-1.016h1v1.11c.157-.057.324-.094.5-.094H18v-1.016h1v1.016h2v-1.016h1v1.016h1.5c.176 0 .343.037.5.094v-1.11h1v1.016zm-4 16.923v-4.728h-1v4.728l-2.119-2.529-.762.66L20.5 34l3.381-4.033-.762-.66L21 31.837zM9.176 17.841l2.489 2.153H6v1.017h5.665l-2.489 2.153.648.774 3.971-3.435-3.971-3.436-.648.774zM34 19.994h-5.665l2.489-2.153-.648-.774-3.971 3.436 3.971 3.435.648-.774-2.489-2.153H34v-1.017zm-16.119-9.3l-.762-.66L20.5 6l3.381 4.034-.762.66L21 8.164v4.717h-1V8.165l-2.119 2.529z" fill="#FFF"></path></g></svg> Auto Scaling Group (Scaling EC2 instances to meet traffic demands)
- <svg class="w-6 h-6" height="40" width="40" xmlns="http://www.w3.org/2000/svg"><defs><linearGradient x1="0%" y1="100%" x2="100%" y2="0%" id="Arch_Amazon-S3-Standard_32_svg__a"><stop stop-color="#1B660F" offset="0%"></stop><stop stop-color="#6CAE3E" offset="100%"></stop></linearGradient></defs><g fill="none" fill-rule="evenodd"><path d="M0 0h40v40H0z" fill="url(#Arch_Amazon-S3-Standard_32_svg__a)"></path><path d="M30.074 22.671l.2-1.301c1.703 1.016 1.735 1.444 1.732 1.46-.004.003-.308.24-1.932-.159zm-10.185-3.733a.995.995 0 01-.992.994.994.994 0 010-1.99c.547 0 .992.448.992.996zm7.869 12.33c0 .123-.495.31-.93.478l-.445.17c-.475.189-1.037.359-1.669.504-1.576.366-3.75.585-5.817.585-5.503 0-8.435-1.009-8.439-1.798L8.256 13.57c1.899 1.452 5.8 2.382 10.641 2.382 4.63 0 9.364-.897 11.584-2.472l-1.366 8.92c-2.871-.874-6.392-2.56-8.132-3.398l-.105-.05.002-.015c0-1.098-.89-1.99-1.983-1.99a1.988 1.988 0 00-1.983 1.99c0 1.097.89 1.99 1.983 1.99.733 0 1.367-.407 1.71-1.002 1.806.868 5.41 2.591 8.356 3.468l-1.205 7.874zm-8.86-23.273c6.676 0 11.857 1.86 11.894 3.465l-.024.148c-.27 1.579-5.352 3.35-11.87 3.35-6.388 0-10.71-1.725-10.89-3.375l-.015-.12c.023-1.678 4.397-3.468 10.904-3.468zm11.538 12.318l1.344-8.76c.001-.026.006-.05.006-.076C31.786 8.674 25.233 7 18.897 7 12.003 7 7 8.883 7 11.477l.003.061 2.468 19.73c0 2.6 7.852 2.732 9.426 2.732 2.137 0 4.394-.228 6.04-.61a12.74 12.74 0 001.81-.548l.432-.167c.844-.321 1.57-.598 1.564-1.331l1.18-7.684c.655.158 1.197.24 1.63.24.58-.001.973-.143 1.21-.428a.982.982 0 00.219-.832c-.127-.681-.923-1.405-2.546-2.327z" fill="#FFF"></path></g></svg> S3 bucket (for object storage)
- <svg class="w-6 h-6" height="40" width="40" xmlns="http://www.w3.org/2000/svg"><defs><linearGradient x1="0%" y1="100%" x2="100%" y2="0%" id="Arch_Amazon-CloudFront_32_svg__a"><stop stop-color="#4D27A8" offset="0%"></stop><stop stop-color="#A166FF" offset="100%"></stop></linearGradient></defs><g fill="none" fill-rule="evenodd"><path d="M0 0h40v40H0z" fill="url(#Arch_Amazon-CloudFront_32_svg__a)"></path><path d="M28 26.497c0-.828-.673-1.5-1.5-1.5s-1.5.672-1.5 1.5c0 .827.673 1.5 1.5 1.5s1.5-.673 1.5-1.5zm1 0a2.503 2.503 0 01-2.5 2.5 2.503 2.503 0 01-2.5-2.5 2.503 2.503 0 012.5-2.501c1.379 0 2.5 1.122 2.5 2.5zm-14-8.004c0-.827-.673-1.5-1.5-1.5s-1.5.673-1.5 1.5c0 .828.673 1.501 1.5 1.501s1.5-.673 1.5-1.5zm1 0a2.503 2.503 0 01-2.5 2.502 2.503 2.503 0 01-2.5-2.502 2.503 2.503 0 012.5-2.5c1.379 0 2.5 1.122 2.5 2.5zm4-8.003c0 .827.673 1.5 1.5 1.5s1.5-.673 1.5-1.5-.673-1.5-1.5-1.5-1.5.673-1.5 1.5zm-1 0a2.503 2.503 0 012.5-2.501c1.379 0 2.5 1.122 2.5 2.501a2.503 2.503 0 01-2.5 2.501 2.503 2.503 0 01-2.5-2.5zm14 9.504c0-4.638-2.485-8.93-6.494-11.25-.721.145-1.416.344-2.28.657l-.34-.94a19.87 19.87 0 011.233-.405A12.95 12.95 0 0020 6.99c-.844 0-1.675.087-2.487.246.587.343 1.108.686 1.615 1.071l-.604.797c-.715-.543-1.457-1-2.426-1.51a13.016 13.016 0 00-9.007 10.963 17.602 17.602 0 013.116-.349l.025 1a16.32 16.32 0 00-3.218.389c-.004.132-.014.267-.014.398 0 4.335 2.146 8.33 5.676 10.736-.627-1.87-.95-3.638-.95-5.36 0-.985.169-1.793.347-2.649l.124-.602.981.193-.125.614c-.176.839-.327 1.562-.327 2.443 0 1.952.432 3.973 1.302 6.166a12.844 12.844 0 009.978.821c.502-.99.875-1.927 1.189-3.009l.961.28c-.228.787-.49 1.5-.801 2.21.804-.361 1.564-.81 2.279-1.33-.173-.426-.35-.85-.554-1.26l.895-.446c.171.343.313.701.463 1.054C31.335 27.377 33 23.83 33 19.995zm1 0c0 4.365-1.982 8.403-5.44 11.079a13.69 13.69 0 01-4.042 2.173c-1.44.5-2.961.754-4.518.754-2.3 0-4.584-.573-6.606-1.659A13.98 13.98 0 016.029 19.15C6.37 13.303 10.377 8.245 16 6.57c3.527-1.063 7.589-.632 10.842 1.208A14.015 14.015 0 0134 19.994zm-15.343-7.272l-.658-.753c-1.12.978-1.992 2.017-3.01 3.586l.838.544c.965-1.485 1.784-2.464 2.83-3.377zm-1.845 7.431c2.296.788 4.299 2.047 6.305 3.96l.69-.722c-2.113-2.018-4.233-3.347-6.67-4.184l-.325.946zm7.011-6.828c1.876 2.862 2.933 6.005 3.14 9.34l-.998.061c-.196-3.158-1.198-6.136-2.978-8.852l.836-.549z" fill="#FFF"></path></g></svg> Cloudfront (for global content delivery)
- <svg class="w-6 h-6" height="40" width="40" xmlns="http://www.w3.org/2000/svg"><defs><linearGradient x1="0%" y1="100%" x2="100%" y2="0%" id="Arch_Amazon-CloudFront_32_svg__a"><stop stop-color="#4D27A8" offset="0%"></stop><stop stop-color="#A166FF" offset="100%"></stop></linearGradient></defs><g fill="none" fill-rule="evenodd"><path d="M0 0h40v40H0z" fill="url(#Arch_Amazon-CloudFront_32_svg__a)"></path><path d="M28 26.497c0-.828-.673-1.5-1.5-1.5s-1.5.672-1.5 1.5c0 .827.673 1.5 1.5 1.5s1.5-.673 1.5-1.5zm1 0a2.503 2.503 0 01-2.5 2.5 2.503 2.503 0 01-2.5-2.5 2.503 2.503 0 012.5-2.501c1.379 0 2.5 1.122 2.5 2.5zm-14-8.004c0-.827-.673-1.5-1.5-1.5s-1.5.673-1.5 1.5c0 .828.673 1.501 1.5 1.501s1.5-.673 1.5-1.5zm1 0a2.503 2.503 0 01-2.5 2.502 2.503 2.503 0 01-2.5-2.502 2.503 2.503 0 012.5-2.5c1.379 0 2.5 1.122 2.5 2.5zm4-8.003c0 .827.673 1.5 1.5 1.5s1.5-.673 1.5-1.5-.673-1.5-1.5-1.5-1.5.673-1.5 1.5zm-1 0a2.503 2.503 0 012.5-2.501c1.379 0 2.5 1.122 2.5 2.501a2.503 2.503 0 01-2.5 2.501 2.503 2.503 0 01-2.5-2.5zm14 9.504c0-4.638-2.485-8.93-6.494-11.25-.721.145-1.416.344-2.28.657l-.34-.94a19.87 19.87 0 011.233-.405A12.95 12.95 0 0020 6.99c-.844 0-1.675.087-2.487.246.587.343 1.108.686 1.615 1.071l-.604.797c-.715-.543-1.457-1-2.426-1.51a13.016 13.016 0 00-9.007 10.963 17.602 17.602 0 013.116-.349l.025 1a16.32 16.32 0 00-3.218.389c-.004.132-.014.267-.014.398 0 4.335 2.146 8.33 5.676 10.736-.627-1.87-.95-3.638-.95-5.36 0-.985.169-1.793.347-2.649l.124-.602.981.193-.125.614c-.176.839-.327 1.562-.327 2.443 0 1.952.432 3.973 1.302 6.166a12.844 12.844 0 009.978.821c.502-.99.875-1.927 1.189-3.009l.961.28c-.228.787-.49 1.5-.801 2.21.804-.361 1.564-.81 2.279-1.33-.173-.426-.35-.85-.554-1.26l.895-.446c.171.343.313.701.463 1.054C31.335 27.377 33 23.83 33 19.995zm1 0c0 4.365-1.982 8.403-5.44 11.079a13.69 13.69 0 01-4.042 2.173c-1.44.5-2.961.754-4.518.754-2.3 0-4.584-.573-6.606-1.659A13.98 13.98 0 016.029 19.15C6.37 13.303 10.377 8.245 16 6.57c3.527-1.063 7.589-.632 10.842 1.208A14.015 14.015 0 0134 19.994zm-15.343-7.272l-.658-.753c-1.12.978-1.992 2.017-3.01 3.586l.838.544c.965-1.485 1.784-2.464 2.83-3.377zm-1.845 7.431c2.296.788 4.299 2.047 6.305 3.96l.69-.722c-2.113-2.018-4.233-3.347-6.67-4.184l-.325.946zm7.011-6.828c1.876 2.862 2.933 6.005 3.14 9.34l-.998.061c-.196-3.158-1.198-6.136-2.978-8.852l.836-.549z" fill="#FFF"></path></g></svg> AWS WAF (Web App Firewall)
- <svg class="w-6 h-6" height="40" width="40" xmlns="http://www.w3.org/2000/svg"><defs><linearGradient x1="0%" y1="100%" x2="100%" y2="0%" id="Arch_Amazon-RDS_32_svg__a"><stop stop-color="#2E27AD" offset="0%"></stop><stop stop-color="#527FFF" offset="100%"></stop></linearGradient></defs><g fill="none" fill-rule="evenodd"><path d="M0 0h40v40H0z" fill="url(#Arch_Amazon-RDS_32_svg__a)"></path><path d="M11.854 28.854L7.708 33H10.5v1h-4a.5.5 0 01-.5-.5v-4h1v2.793l4.147-4.146.707.707zM33 29.5h1v4c0 .277-.223.5-.5.5h-4v-1h2.793l-4.146-4.146.707-.707L33 32.293V29.5zm1-23v4h-1V7.708l-4.146 4.146-.707-.707L32.293 7H29.5V6h4a.5.5 0 01.5.5zm-27 4H6v-4a.5.5 0 01.5-.5h4v1H7.527l4.319 4.14-.691.721L7 7.88v2.62zm25.726 8.9c0-1.558-1.806-3.1-4.83-4.123l.32-.947c3.502 1.185 5.51 3.033 5.51 5.07 0 2.037-2.008 3.886-5.51 5.071l-.32-.948c3.024-1.023 4.83-2.565 4.83-4.123zm-24.989 0c0 1.492 1.69 2.993 4.521 4.014l-.34.94c-3.293-1.187-5.181-2.993-5.181-4.954 0-1.961 1.888-3.767 5.181-4.955l.34.941c-2.831 1.021-4.521 2.522-4.521 4.014zm12.286-3.681c-3.136 0-4.891-.799-4.917-1.125.026-.326 1.781-1.125 4.917-1.125 3.133 0 4.89.798 4.917 1.125-.027.326-1.784 1.125-4.917 1.125zm0 3.555c-3.182 0-4.917-.926-4.917-1.402v-2.03c1.135.595 3.069.877 4.917.877 1.848 0 3.782-.282 4.917-.877v2.03c0 .476-1.735 1.402-4.917 1.402zm0 3.737c-3.182 0-4.917-.927-4.917-1.403v-2.343c1.119.665 3.023 1.009 4.917 1.009 1.894 0 3.798-.344 4.917-1.009v2.343c0 .476-1.735 1.403-4.917 1.403zm0 3.279c-3.182 0-4.917-.915-4.917-1.385v-1.904c1.119.666 3.023 1.01 4.917 1.01 1.894 0 3.798-.344 4.917-1.01v1.904c0 .47-1.735 1.385-4.917 1.385zm0-13.821c-2.85 0-5.917.665-5.917 2.125v10.311c0 1.566 2.977 2.385 5.917 2.385s5.917-.819 5.917-2.385V14.594c0-1.46-3.067-2.125-5.917-2.125z" fill="#FFF"></path></g></svg> RDS (Mysql for database)

- <svg class="w-6 h-6" height="40" width="40" xmlns="http://www.w3.org/2000/svg"><defs><linearGradient x1="0%" y1="100%" x2="100%" y2="0%" id="Arch_AWS-Certificate-Manager_32_svg__a"><stop stop-color="#BD0816" offset="0%"></stop><stop stop-color="#FF5252" offset="100%"></stop></linearGradient></defs><g fill="none" fill-rule="evenodd"><path d="M0 0h40v40H0z" fill="url(#Arch_AWS-Certificate-Manager_32_svg__a)"></path><path d="M17.832 19.63c.133.12.19.3.152.476l-.513 2.362 2.27-1.391a.496.496 0 01.52 0l2.252 1.388-.498-2.367a.5.5 0 01.15-.47l2.014-1.84-2.665-.515a.496.496 0 01-.352-.27l-1.166-2.387-1.194 2.394a.497.497 0 01-.35.265l-2.657.518 2.037 1.838zm-1.58 3.765l.701-3.22-2.562-2.312a.498.498 0 01.237-.856l3.393-.66 1.534-3.075c.085-.17.286-.306.447-.276.19.001.362.11.445.28l1.5 3.068 3.39.656a.498.498 0 01.241.854l-2.533 2.316.68 3.223a.498.498 0 01-.748.525L20 22.083l-3.002 1.84a.492.492 0 01-.548-.018.495.495 0 01-.198-.51zm16.727-13.3l-.003-2.101H6.994v2.101h25.985zM34 32.502a.496.496 0 01-.497.498h-3.566v-.994h3.07L32.98 11.09H6.994v20.917h18.968V33H6.497a.5.5 0 01-.352-.145.5.5 0 01-.145-.352V7.497C6 7.223 6.222 7 6.497 7H33.47c.276 0 .497.223.497.497L34 32.502zm-22.942-2.527h3.974v-.993h-3.974v.993zm5.962.023h6.955v-.993H17.02v.993zm-5.962-3h3.974v-.993h-3.974v.994zm5.962 0h10.93v-.993H17.02v.994z" fill="#FFF"></path></g></svg> ACM (SSL certificate)
---

## STEPS 

1. Purchased the domain name in Route 53
2. Launched an ec2 instance (t2 micro, Amazon Linux)
   - configure the security group inbound rule of the ec2 instance to allow ssh on port 22, http on port 80 and https on port 443

3. Installed the LAMP stack on the ec2 instance 
   ```bash 
   # connecting to ec2 instance
   ssh -i <path-to-your-key-pair> ec2-user@<your-instance-public-ip>

   # updating the system packages 
   sudo yum update -y

   # Install the apache webserver
   sudo yum install -y httpd

   # install PHP
   sudo yum install -y php 

   # install additional PHP extension
   sudo yum install -y php-mysqlnd

   #install the database 
   sudo yum install Mariadb105-server Mariadb-client

   # start the server
   sudo systemctl start httpd 
   sudo systemctl enable httpd

   # add the ec2-user to the 'apache' group on the Linux system
   sudo usermod -a -G apache ec2-user

   # recursively change the ownership of all files and directories within /var/www to the user ec2-user and the group apache. 
   sudo chown -R ec2-user:apache /var/www
   
   # allowing the owner and group to have full read, write, and execute access.
   sudo chmod 2775 /var/www
   find /var/www -type d -exec sudo chmod 2775 {} +
   find /var/www -type f -exec sudo chmod 0664 {} +

   ```

4. Set up Mysql database for Wordpress 
   ```bash
   sudo mysql -u root
   CREATE DATABASE wordpress;
   CREATE USER 'wordpress'@'localhost' IDENTIFIED BY 'your_password';
   GRANT ALL PRIVILEGES ON wordpress.* TO 'wordpress'@'localhost';
   FLUSH PRIVILEGES;
   EXIT;
   ```
5. Download and configure Wordpress
   ```bash
   # change directory
   cd /var/www/html

   # download wordpress
   sudo wget https://wordpress.org/latest.tar.gz

   # Extract wordpress files
   sudo tar -xzf latest.tar.gz

   # Move all files from wordpress to the current directory
   sudo mv wordpress/* .

   # remove the wordpress directory and the latest.tar.gz file from the current directory
   sudo rm -rf wordpress latest.tar.gz

   # the ownership of the /var/www/html directory and all its files and subdirectories will be changed to the apache user and apache group
   sudo chown -R apache:apache /var/www/html

   ```
6. Run your ec2 instance public IP in browser to check if all the Installation worked. If it worked, You will see a wordpress webpage asking you to connect to your database. 

---
   
###  NOW THAT YOUR WORDPRESS WEBSITE IS WORKING, IT IS TIME TO SCALE OUR WORDPRESS WEBSITE  
1. Now on your EC2 instance dashboard, create a target group with the EC2 Instance as a target. 
   
2. Create an application load balancer. Configure the ALB listener to listen to listen on port 80 and forward traffic to the target group.  
3. Run the ALB DNS name in the browser. If the wordpress page appears that mean it is working.
4. Request for an SSL certificate in ACM. The name should be the same as the name you bought in Route 53.
   
5. Configure Cloudfront with the ALB as the origin. 
   - In the origin protocol, select Http port only
   - In the settings, under the alternate domain name, type out the domain name I bought in Route 53
   - Under custom SSL certificate, select the SSL certificate you requested in ACM.
   - Enable AWF WAF in Cloudfront. 
