<template>
  <div class="container">
    <div class="first-box">
      <h2>Mobile Games Tournament  2021</h2>
      <h4>PES & CODM</h4>
    </div>
    <div class="pes">
      <img src="../assets/messi.png" alt="messi">
    </div>
    <div class="cod">
      <img src="../assets/codsoldier.png" alt="cod">
    </div>
    <div class="ad">
      <p>Do you want to participate in a one of a kind campus based mobile game tournament and win cash prizes?</p>
    </div>
    <div class="howto">
      <h3>How to register</h3>
      <li>A registration fee of #5,000</li>
      <li>Name</li>
      <li>Faculty</li>
      <li>Department</li>
      <li>Game interested in</li>
      <li>UserId</li>
      <button>Register</button>
    </div>
    <div class="rules">
      <h3>Rules & Regulation of the tournament</h3>
      <li>Lorem ipsum dolor sit amet.</li>
      <li>Lorem ipsum dolor sit amet consectetur adipisicing elit.</li>
      <li>Lorem ipsum dolor sit amet consectetur adipisicing.</li>
      <li>Lorem ipsum dolor sit amet consectetur adipisicing.</li>
      <li>Lorem ipsum dolor sit amet, consectetur adipisicing.</li>
    </div>
    <div class="enquiries">
      <h4>For more enquiries and sponsorships:</h4>
      <div class="contact">
        MJ - <span>08171464003</span>, Saybudu - <span>08103840212,</span> Williams - <span>09034696604</span>
      </div>
    </div>
  </div>
</template>

<script>
export default {

}
</script>

<style>
  .container {
    padding-inline: 1.2rem;
    padding-top: 3rem;
  }

  .first-box {
    text-align: center;
  }

  .first-box h2 {
    font-size: 1.8rem;
    color: #03045E;
  }

  .first-box h4 {
    font-size: 1.24em;
    color: #0077B6;
  }

  .pes {
    margin-block: 2rem;
    /* background-color: #0077B6; */
    background: rgb(237,188,0);
    background: radial-gradient(circle, rgba(237,188,0,1) 0%, rgba(0,76,153,1) 35%, rgba(167,0,66,1) 100%);
    border-radius: 20px;
  }

  .pes img {
    width: 100%;
    height: 100%;
  }

  .cod {
    margin-block: 2rem;
    padding: .4rem;
    background-color: #2100b6;
    border-radius: 20px;
  }

  .cod img {
    width: 100%;
    height: 100%;
  }

  .ad {
    text-align: center;
    padding-inline: 2rem;
  }

  .ad p {
    font-family: 'Cookie', cursive;
    font-size: 1.8rem;
    font-weight: 600;
    color: #232425;
  }

  .howto {
    margin-block: 2rem;
    background-color: #232425;
    padding: 1rem;
    border-radius: 20px;
    color: #fff;
    box-shadow: -4.5px 6px 13.5px -3.5px #938181;
  }

  .howto h3,
  .rules h3 {
    padding-bottom: 1.2rem;
  }

  .howto li {
    list-style: none;
    font-size: 1.1rem;
    padding-block: .2rem;
    color: #c5c0c0;
  }

  .howto button {
    border: none;
    margin-block: .6rem;
    padding: .8rem 1.3rem;
    border-radius: 20px;
    background-color: #fff;
    color: #000;
    font-size: 1rem;
    font-weight: 600;
  }

  .rules {
    margin-block: 2rem;
    background: #e0e0e0;
    box-shadow:  20px 20px 60px #bebebe, -20px -19px 20px #ffffff;
    padding: 1rem;
    border-radius: 20px;
    color: rgb(26, 24, 24);
  }

  .rules li {
    list-style: none;
    font-size: 1.1rem;
    padding-block: .2rem;
    color: #232425;
  }

  .enquiries {
    margin-bottom: 1rem;
  }

  .contact {
    font-family: 'Cookie', cursive;
    background-color: #232425;
    color: #fff;
    text-align: center;
    margin-block: .3rem;
    padding: .1rem .5rem;
    font-size: .9rem;
    border-radius: 20px;
  }

  .contact span {
    font-family: 'Source Sans Pro', sans-serif;
    color: #c5c0c0;
  }
</style>