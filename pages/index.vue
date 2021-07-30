<template>
  <div>
    <div id="capture" ref="element" style="padding: 10px; background: #f5da55">
      <h4 style="color: #000">Hello world!</h4>
    </div>

    <br />
    <div>hehe</div>
    <p>
      Chuck Norris doesn't churn butter. He roundhouse kicks the cows and the
      butter comes straight out. When the Boogeyman goes to sleep every night,
      he checks his closet for Chuck Norris CNN was originally created as the
      "Chuck Norris Network" to update Americans with on-the-spot ass kicking in
      real-time. Chuck Norris was an only child...eventually Chuck Norris is the
      only man to ever defeat a brick wall in a game of tennis. Chuck Norris
      invented Kentucky Fried Chicken's famous secret recipe, with eleven herbs
      and spices. But nobody ever mentions the twelfth ingredient: Fear Chuck
      Norris has two speeds. Walk, and Kill. Chuck Norris doesn't read books. He
      stares them down until he gets the information he wants. Chuck Norris does
      not sleep. He waits. Police label anyone attacking Chuck Norris as a Code
      45-11... a suicide Someone once videotaped Chuck Norris getting pissed
      off. It was called Walker: Texas Chain Saw Massacre. Chuck Norris does not
      get frostbite. Chuck Norris bites frost. Police label anyone attacking
      Chuck Norris as a Code 45-11... a suicide. Chuck Norris can write a letter
      by using sign language. Chuck Norris is currently suing NBC, claiming Law
      and Order are trademarked names for his left and right legs.
    </p>

    <p>
      Go into a room to decide you didn't want to be in there anyway be
      superior. Run outside as soon as door open what a cat-ass-trophy! meowing
      chowing and wowing meow meow mama head nudges and cats go for world
      domination. Stand with legs in litter box, but poop outside while happily
      ignoring when being called yet good morning sunshine mouse scratch at the
      door then walk away. Push your water glass on the floor crusty butthole
      and chirp at birds for fight an alligator and win. Sniff all the things
      nap all day there's a forty year old lady there let us feast thug cat a
      nice warm laptop for me to sit on or please stop looking at your phone and
      pet me but sniff catnip and act crazy. Stare at ceiling toilet paper
      attack claws fluff everywhere meow miao french ciao litterbox look at dog
      hiiiiiisssss.
    </p>

    <h2>Nice title</h2>
    <section>
      We need to future-proof this win-win-win. Great plan! Let me diarize this,
      and we can synchronize ourselves at a later timeframe, for strategic
      staircase wiggle room. Idea shower: what's our go to market strategy?
      Table the discussion; I just wanted to give you a heads-up, and run it up
      the flag pole for a performance review. It's a simple lift and shift job.
      Throughput criticality, pre-think our game-plan. So if you could do that,
      that would be great for critical mass. Pull in ten extra bodies to help
      roll the tortoise, a loss a day will keep you focused, then loop back.
      Back-end of third quarter, meeting assassins get buy-in to close the loop.
      When does this sun set?
    </section>
    <br />
    <button @click="share">share please</button>
  </div>
</template>

<script>
import html2canvas from 'html2canvas'

export default {
  methods: {
    // iife here!
    share() {
      ;(async () => {
        if (!('share' in navigator)) {
          return
        }
        // `element` is the HTML element you want to share.
        // `backgroundColor` is the desired background color.
        const canvas = await html2canvas(this.$refs.element)
        canvas.toBlob(async (blob) => {
          // Even if you want to share just one file you need to
          // send them as an array of files.
          const files = [new File([blob], 'image.png', { type: blob.type })]
          const shareData = {
            text: 'Some text',
            title: 'Some title',
            files,
          }
          if (navigator.canShare(shareData)) {
            try {
              await navigator.share(shareData)
            } catch (err) {
              if (err.name !== 'AbortError') {
                console.error(err.name, err.message)
              }
            }
          } else {
            console.warn('Sharing not supported', shareData)
          }
        })
      })()
    },
  },
}
</script>
