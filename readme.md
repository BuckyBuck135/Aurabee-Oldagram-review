What you've done well:
 - the app looks great
 - custom fonts
 - lots of comments on HTML and CSS
 - applying the container technique
 - use of <article> tags
 - use of * and box-sizing, utility classes, em units, shorthand declarations

 What could be improved:
 [] HTML
- .main not used
- added <main> to wrap all main post content
- could add footer if wanted to
- reworked post markup:
  - each post is an <article> containing info + photo + icons + likes + comments
  - BUT all that content is nested inside a .container that will constrain the content to the desired width
  - info-wrapper / post-el-wrapper is a div, not article
  - .card-container is deleted. the margin is applied to each <article>
  - .container is reworked: no more flex-wrap and width which create layout issues => width: 100%; max-width: 600px;
  - .likes-el and post-content can be removed, keeping the <p> and <h3> elements as direct children

[] CSS
- the flex-wrap and width on the container were crutches that masked the issues of the HTML markup. Remember that the less we write, the fewer problems we create lol
  
<!-- MY VERSION -->
        <header> 
            <div class="container header-imgs">
                <img src="images/logo.png" class="logo-img">
                <img src="images/pinkhair-avatar.png" class="avatar-img">
            </div>
        </header>
        <main>
            <article> 
                <div class="container">
                    <div class="info-wrapper"> 
                        <img src="images/avatar-vangogh.jpg" class="avatar-img" id="avatar-img">
                        <div class="info-text">
                            <h3 class="name-text"> Vincent Van Gogh </h3>
                            <p class="location-text"> Zundert, Netherlands</p>
                        </div>
                    </div>
            
                    <div class="article-info-img">
                        <img class="article-img" src="images/post-vangogh.jpg">
                    </div> 
                    
                    <div class="posts-el-wrapper"> 
                        <div class="icons-el">
                            <img src="images/icon-heart.png" class="icon-img">
                            <img src="images/icon-comment.png" class="icon-img">
                            <img src="images/icon-dm.png" class="icon-img">
                        </div>
                        
                        <div class="likes-el">
                            <p class="likes-text bold-text"> 21,1492 Likes </p>
                        </div>
                        
                        <div class="post-content">
                            <h3 class="tag-line">vincey1853 <span class="lighter-text">  just took some mushrooms, innit</span></h3>
                        </div> 
                    </div>               
                </div> 
            </article>
        </main>