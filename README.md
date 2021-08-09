# PeerPal: A Peer Grading Platform

This project serves to help improve learning outcomes, foundationally by enabling students to grade each other's submissions, but also through a series of innovative features designed to track and improve the learning experience in more ways than one.

## Project Team

This project's development is managed by a team of Northwestern Students supervised by Jason Hartline, funded by NSF. For any questions an concerns, [contact us here.](mailto:peerpal.io+os@gmail.com)

<!--
*** Thanks for checking out the Best-README-Template. If you have a suggestion
*** that would make this better, please fork the repo and create a pull request
*** or simply open an issue with the tag "enhancement".
*** Thanks again! Now go create something AMAZING! :D
-->



<!-- PROJECT SHIELDS -->
<!--
*** I'm using markdown "reference style" links for readability.
*** Reference links are enclosed in brackets [ ] instead of parentheses ( ).
*** See the bottom of this document for the declaration of the reference variables
*** for contributors-url, forks-url, etc. This is an optional, concise syntax you may use.
*** https://www.markdownguide.org/basic-syntax/#reference-style-links
-->
[![Contributors][contributors-shield]][https://github.com/nu-peerpal/Peer-Grading-Hosting/graphs/contributors]
[![Forks][forks-shield]][https://github.com/nu-peerpal/Peer-Grading-Hosting/network/members]
[![Stargazers][stars-shield]][https://github.com/nu-peerpal/Peer-Grading-Hosting/stargazers]
[![Issues][issues-shield]][https://github.com/nu-peerpal/Peer-Grading-Hosting/issues]
<!-- [![MIT License][license-shield]][license-url]
[![LinkedIn][linkedin-shield]][linkedin-url] -->



<!-- PROJECT LOGO -->
<br />
<p align="center">
  <a href="https://github.com/othneildrew/Best-README-Template">
    <img src="images/logo.png" alt="Logo" width="80" height="80">
  </a>

  <h3 align="center">PeerPal: A Peer Grading Platform</h3>

  <p align="center">
    Enhancing learning outcomes through peer granding and more!
    <br />
    <a href="www.peerpal.io"><strong>Explore the docs »</strong></a>
    <br />
    <br />
    <a href="www.peerpal.io">View Demo</a>
    ·
    <a href="https://github.com/nu-peerpal/Peer-Grading-Hosting/issues">Report Bug</a>
    ·
    <a href="https://github.com/nu-peerpal/Peer-Grading-Hosting/issues">Request Feature</a>
  </p>
</p>



<!-- TABLE OF CONTENTS -->
<details open="open">
  <summary>Table of Contents</summary>
  <ol>
    <li>
      <a href="#about-the-project">About The Project</a>
      <ul>
        <li><a href="#built-with">Built With</a></li>
      </ul>
    </li>
    <li>
      <a href="#getting-started">Getting Started</a>
      <ul>
        <li><a href="#prerequisites">Prerequisites</a></li>
        <li><a href="#installation">Installation</a></li>
      </ul>
    </li>
    <li><a href="#usage">Usage</a></li>
    <li><a href="#roadmap">Roadmap</a></li>
    <li><a href="#contributing">Contributing</a></li>
    <li><a href="#license">License</a></li>
    <li><a href="#contact">Contact</a></li>
    <li><a href="#acknowledgements">Acknowledgements</a></li>
  </ol>
</details>



<!-- ABOUT THE PROJECT -->
## About The Project

[![PeerPal Screen Shot][product-screenshot]](https://example.com)

PeerPal is a project founded by Jason Hartline [among others to be named, Jacob Collins, Leif Rasmussen were original developers?], under the simple proposition that allowing students to grade each others’ assignments can actually improve learning outcomes. However, this premise can go beyond just the benefits of students analyzing other students’ assignments.

Imagine a more involved system where students can learn from each other and make more informed decisions about how to efficiently complete their coursework based on key performance indicators, such as time spent on their peer reviews, whether or not they attend office hours regularly, or generally gaining deeper insight into how historical data can inform current students’ learning decisions (especially in a learning environment where every hour spent on your work could be spent doing some other work).


### About Peer Grading
A peer grading system is an online tool that collects student submissions, and assigns review tasks to the students and teacher, and aggregates reviews to produce assessments of both the submissions and the peer reviews.  The potential benefits of the a peer review system are as follows:
1.  Learning by reviewing:  Students learn from critical assessment of other students’ work.  In an early prototype of Peer Pal 60% of the students reported that peer review helped them learn course material and 55% of the students reported that peer review helped them to prepare better homework solutionsthemselves.
2.  Reduced teacher grading:  Peer grading system reduces the grading load on the teacher which frees the  teacher  to  do  other  tasks  and  enables  the  teacher  to  effectively  manage  larger  class  sizes,  both of these consequences of reduced teacher grading could improve education outcomes.  In the Peer Pal prototype, the course staff graded 1/5 of the student submissions.
3.  Promptness of feedback:  Reduced teacher grading and distributing enables prompt feedback to students.  In the prototype, peer reviews were available within three days and final assessment of both the  submission  and  peer  reviews  were  available  within  five  days.   Prior  to  introducing  peer  review, assessments took one two two weeks.
4.  Identifying early warnings:  Peer review systems collect a large amount of data that can be mined to identify under performing students and suggest interventions.

### Built With

* [Material-UI](https://material-ui.com)
* [Next.JS](https://nextjs.org) 
* [AWS](https://aws.amazon.com)



<!-- GETTING STARTED -->
## Getting Started

There are several components that work together for this project to run smoothly. Notably, the platform is built to sync with an instance of Canvas, but uses its own database and storage entities to remove obstacles involved with Canvas data management. If you are starting your own version of this project from scratch and want a more in-depth tutorial, please refer to our [PeerPal from Scratch Guide.](www.peerpal.io)

### Prerequisites

* npm
  ```sh
  npm install npm@latest -g
  ```
* Create/set up Amazon RDS Database
* Create/set up AWS S3 Bucket for submissions
* Set up a development instance of Canvas

### Installation

1. Clone the repo
   ```sh
   git clone https://github.com/nu-peerpal/Peer-Grading-Hosting.git
   ```
2. Install NPM packages in project directory
   ```sh
   npm install
   ```
3. Create a new file in the root directory named `.env.local`. Note that these values should not end up having quotes around them.
   ```JS
    DB_URI = "URI for database connection"
    CANVAS_TOKEN = "LTI Secret shared for Canvas Dev Server External Tool Configuration"
    CANVAS_SECRET = "Secret shared with Canvas tool config"
    AWS_ID = "AWS CLI ID with read/write access to Submissions S3 Bucket"
    AWS_SECRET = "Corresponding AWS secret"
    SUBMISSIONS_BUCKET = "Name of Submissions S3 Bucket"
    CANVAS_TOKEN = "Canvas API Key from a user with at least TA privileges for the course"
    CONTENT_ID = "LTI Configuration for External Tool"
    RESOURCE_LINK_ID = "LTI Configuration for External Tool"
    LAUNCH_URL = "http://localhost:8081"
   ```
4. Start your development environment
    ```sh
   npm run dev
   ```
5. Launch PeerPal by going into your Canvas server, configuring an assignment with your launch URL (http://localhost8081), going into that assignment and launching in a new tab.



<!-- USAGE EXAMPLES -->
## Usage

1. Initialize your peer review assignment from an existing Canvas assignment (only accept PDF submissions)
2. Collect submissions via the Canvas assignment, wait for due date to pass.
3. Run the peer matching algorithm and confirm matchings to assign peer reviews.
4. Students will be assigned their peer review assignment in Canvas, where they can launch into PeerPal and conduct their reviews. Wait for this deadline to pass.
5. Run the additional matches algorithm to determine whether or not you need to assign any additional TA reviews.
6. Instruct your assigned TA to conduct the TA reviews via the "TA Grading" tab, TA must confirm when complete.
7. Run the review and submission reports algorithms. If everything looks good, approve and the reports will be delivered to students on PeerPal.
8. Set up the Appeals deadline and instruct students to submit appeals for their assignments if they would like.
9. Once the Appeals deadline passes and the TA has completed any additional reviews, review the grades and submit to Canvas.

_For more examples, please refer to the [Documentation](https://example.com)_



<!-- ROADMAP -->
## Roadmap

See the [open issues](https://github.com/nu-peerpal/Peer-Grading-Hosting/issues) for a list of proposed features (and known issues).



<!-- CONTRIBUTING -->
## Contributing

Contributions are what make the open source community such an amazing place to be learn, inspire, and create. Any contributions you make are **greatly appreciated**.

1. Fork the Project
2. Create your Feature Branch (`git checkout -b feature/NewFeature`)
3. Commit your Changes (`git commit -m 'Add some NewFeature'`)
4. Push to the Branch (`git push origin feature/NewFeature`)
5. Open a Pull Request



<!-- LICENSE -->
## License

Distributed under the MIT License. See `LICENSE` for more information.



<!-- CONTACT -->
## Contact

Jason Hartline - [jasonhartline.com](https://sites.northwestern.edu/hartline/) - peerpal.io@gmail.com

Project Link: [https://github.com/nu-peerpal/Peer-Grading-Hosting](https://github.com/nu-peerpal/Peer-Grading-Hosting)



<!-- ACKNOWLEDGEMENTS -->
## Acknowledgements
* [GitHub Emoji Cheat Sheet](https://www.webpagefx.com/tools/emoji-cheat-sheet)
* [Img Shields](https://shields.io)
* [Choose an Open Source License](https://choosealicense.com)
* [GitHub Pages](https://pages.github.com)
* [Animate.css](https://daneden.github.io/animate.css)
* [Loaders.css](https://connoratherton.com/loaders)
* [Slick Carousel](https://kenwheeler.github.io/slick)
* [Smooth Scroll](https://github.com/cferdinandi/smooth-scroll)
* [Sticky Kit](http://leafo.net/sticky-kit)
* [JVectorMap](http://jvectormap.com)
* [Font Awesome](https://fontawesome.com)





<!-- MARKDOWN LINKS & IMAGES -->
<!-- https://www.markdownguide.org/basic-syntax/#reference-style-links -->
[contributors-shield]: https://img.shields.io/github/contributors/othneildrew/Best-README-Template.svg?style=for-the-badge
[contributors-url]: https://github.com/othneildrew/Best-README-Template/graphs/contributors
[forks-shield]: https://img.shields.io/github/forks/othneildrew/Best-README-Template.svg?style=for-the-badge
[forks-url]: https://github.com/othneildrew/Best-README-Template/network/members
[stars-shield]: https://img.shields.io/github/stars/othneildrew/Best-README-Template.svg?style=for-the-badge
[stars-url]: https://github.com/othneildrew/Best-README-Template/stargazers
[issues-shield]: https://img.shields.io/github/issues/othneildrew/Best-README-Template.svg?style=for-the-badge
[issues-url]: https://github.com/othneildrew/Best-README-Template/issues
[license-shield]: https://img.shields.io/github/license/othneildrew/Best-README-Template.svg?style=for-the-badge
[license-url]: https://github.com/othneildrew/Best-README-Template/blob/master/LICENSE.txt
[linkedin-shield]: https://img.shields.io/badge/-LinkedIn-black.svg?style=for-the-badge&logo=linkedin&colorB=555
[linkedin-url]: https://linkedin.com/in/othneildrew
[product-screenshot]: images/screenshot.png

## License

This repository is licensed under [CC-BY-4.0](../LICENSE) (c) 2019 GitHub, Inc.
