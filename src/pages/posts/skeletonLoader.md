---
title: Skeleton loadder UI using HTML & CSS
slug: skeleton-loadder-ui-using-html-css
date: 2021-7-25
author: Atharva Joshi
read_time: 4
tags: ["HTML", "CSS"]
order: 3
hero: https://raw.githubusercontent.com/atharva20-coder/devatharva.com/master/src/images/posts/htm-css-js/skeleton.png
draft: false
emoji: "💀"
---

### Build a simple Skeleton Card loader component using <img src="https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white" style="vertical-align:middle" alt="react-background"> and <img src="https://img.shields.io/badge/CSS-239120?&style=for-the-badge&logo=css3&logoColor=white" style="vertical-align:middle" alt="react-background">.

**Hello geeks👋** In this tutorial, let's build a simple skeleton loader component using HTML and CSS. You can then use this component in your websites/apps as a fallback option before your main content loads.

We will create a card and its skeleton loader, so let's start with adding the HTML for both the card and the skeleton.

## HTML for the card

```html
<div class="card">
  <div>
    <img class="card-img"
    src="https://avataaars.io/?avatarStyle=Transparent&topType=ShortHairShortWaved&accessoriesType=Prescription01&hairColor=Black&facialHairType=Blank&clotheType=Hoodie&clotheColor=Blue03&eyeType=Default&eyebrowType=Default&mouthType=Twinkle&skinColor=Light"
    / alt="skeleton loader">
  </div>
  <div class="card-text">
    <h2 class="card-title">Atharva Joshi</h2>
    <p class="card-description">
      <span>Lorem ipsum dolor sit amet consectetur, adipisicing eli.</span>
    </p>
    <ul class="card-skills">
      <li class="skill">UI Designer.</li>
      <li class="skill">UX Designer.</li>
      <li class="skill">Web Developer.</li>
    </ul>
    <a href="#" class="card-link">Read More</a>
  </div>
</div>
```

# HTML for skeleton 💀

**(We are going to keep the basic structure the same as the card but we will remove the content. Also, change the classes on the elements')**

```html
<div class="skeleton">
  <div class="skeleton-img"></div>
  <div class="skeleton-text">
    <h2 class="skeleton-title"></h2>
    <p class="skeleton-description">
      <span></span>
      <span></span>
    </p>
    <ul class="skeleton-skills">
      <li class="skill"></li>
      <li class="skill"></li>
      <li class="skill"></li>
    </ul>
    <a href="#" class="skeleton-link"></a>
  </div>
</div>
```

# Step 2 - Adding the common styles for the card and the skeleton.

(For the consistent look)

```css
.card,
.skeleton {
  display: flex;
  justify-content: space-around;
  padding: 20px;
  max-width: 400px;
  height: 155px;
  margin: 20px;
  border-radius: 10px;
  background-color: #e2e8f0;
  box-shadow: 0 9px 33px rgba(0, 0, 0, 0.07);
}

.card-text,
.skeleton-text {
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  width: 250px;
  margin-left: 10px;
}

.card-img,
.skeleton-img {
  width: 75px;
  height: 75px;
  border-radius: 50%;
}

.card-description,
.skeleton-description {
  margin: 10px 0;
}

.card-link,
.skeleton-link {
  margin-top: 20px;
}

.card-skills,
.skeleton-skills {
  display: flex;
  justify-content: space-between;
}
```

# Step 3 - Adding the Card-specific styles.

(Font sizes, colors, etc)

```css
.card-img {
  background-color: #4f46e5;
}

.card-title {
  font-size: 16px;
  color: #334155;
}

.card-description {
  font-size: 12px;
  color: #64748b;
}

.card-skills .skill {
  font-size: 12px;
  font-weight: 600;
  color: #475569;
}

.card-link {
  font-size: 12px;
  color: #4f46e5;
}
```

# Step 4 - Adding the skeleton specific styles

(Here, we will specify the height, width, and background color of the skeletons.)

```css
.skeleton-img {
  animation: pulse 2s infinite ease-in-out;
}

.skeleton-description span:nth-child(1) {
  display: block;
  width: 210px;
  height: 10px;
  background-color: #94a3b8;
}

.skeleton-description span:nth-child(2) {
  display: block;
  width: 150px;
  height: 10px;
  background-color: #94a3b8;
  margin-top: 5px;
}

.skeleton-skills .skill {
  width: 65px;
  height: 12px;
  background-color: #94a3b8;
}

.skeleton-link {
  width: 75px;
  height: 12px;
  background-color: #94a3b8;
}
```

Now The card and the skeleton should look like this

<img src="/src/images/posts/htm-css-js/skeleton.png" alt="skeleton loader">

**We are almost there! Now let's add the subtle animation on the skeletons**

# Step 5 - Adding the animation

```css
@keyframes pulse {
  0% {
    background-color: #94a3b8;
  }

  50% {
    background-color: #cbd5e1;
  }

  100% {
    background-color: #94a3b8;
  }
}
```

**Now we can add this animation on all the skeletons and remove the background color.**

```css
/** replace all styles from skeletons with these styles */

.skeleton-title {
  width: 150px;
  height: 12px;
  animation: pulse 2s infinite ease-in-out;
}

.skeleton-img {
  animation: pulse 2s infinite ease-in-out;
}

.skeleton-description span:nth-child(1) {
  display: block;
  width: 210px;
  height: 10px;
  animation: pulse 2s infinite ease-in-out;
}

.skeleton-description span:nth-child(2) {
  display: block;
  width: 150px;
  height: 10px;
  animation: pulse 2s infinite ease-in-out;
  margin-top: 5px;
}

.skeleton-skills .skill {
  width: 65px;
  height: 12px;
  animation: pulse 2s infinite ease-in-out;
}

.skeleton-link {
  width: 75px;
  height: 12px;
  animation: pulse 2s infinite ease-in-out;
}
```

**Final Demo**

<video width="100%" height="100%" autoplay loop alt="skeleton loader card">
  <source src="/src/images/posts/htm-css-js/skeleton.mp4" type="video/mp4"/>
</video>

<br><br><br>
