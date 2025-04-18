# Ramesh-
Ramesh luni 
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Education App</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      margin: 0;
      padding: 0;
      background-color: #f5f5f5;
    }
    header {
      background-color: #4CAF50;
      color: white;
      padding: 1rem;
      text-align: center;
    }
    .container {
      padding: 2rem;
    }
    .course-list {
      display: flex;
      flex-wrap: wrap;
      gap: 1rem;
    }
    .course {
      background: white;
      border: 1px solid #ccc;
      border-radius: 8px;
      padding: 1rem;
      width: 300px;
      cursor: pointer;
      transition: 0.3s;
    }
    .course:hover {
      box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
    }
    #course-detail {
      display: none;
      background: white;
      padding: 1rem;
      margin-top: 2rem;
      border-radius: 8px;
    }
    iframe {
      width: 100%;
      height: 315px;
      border: none;
      margin-top: 1rem;
    }
  </style>
</head>
<body>
  <header>
    <h1>My Education App</h1>
  </header>
  <div class="container">
    <h2>Available Courses</h2>
    <div class="course-list" id="course-list"></div>
    <div id="course-detail">
      <h3 id="course-title"></h3>
      <p id="course-description"></p>
      <iframe id="course-video" allowfullscreen></iframe>
    </div>
  </div>

  <script>
    const courses = [
      {
        title: "HTML Basics",
        description: "Learn the basics of HTML.",
        videoUrl: "https://www.youtube.com/embed/UB1O30fR-EE"
      },
      {
        title: "CSS Fundamentals",
        description: "Understand how to style your website using CSS.",
        videoUrl: "https://www.youtube.com/embed/yfoY53QXEnI"
      },
      {
        title: "JavaScript Introduction",
        description: "Start your JavaScript journey here.",
        videoUrl: "https://www.youtube.com/embed/W6NZfCO5SIk"
      }
    ];

    const courseListEl = document.getElementById("course-list");
    const detailEl = document.getElementById("course-detail");
    const titleEl = document.getElementById("course-title");
    const descEl = document.getElementById("course-description");
    const videoEl = document.getElementById("course-video");

    courses.forEach((course, index) => {
      const div = document.createElement("div");
      div.className = "course";
      div.innerHTML = `<h3>${course.title}</h3><p>${course.description}</p>`;
      div.onclick = () => {
        titleEl.innerText = course.title;
        descEl.innerText = course.description;
        videoEl.src = course.videoUrl;
        detailEl.style.display = "block";
      };
      courseListEl.appendChild(div);
    });
  </script>
</body>
</html>
