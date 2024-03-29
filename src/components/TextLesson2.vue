<template>
  <div class="is-info content" :id="this.tileNo">
    <div>
      <div class="has-text-link-dark has-text-left title is-5 is-json" >
          Lesson 4: Let it shell<span>&#35;</span>, let it shell<span>&#35;</span>, let it shell<span>&#35;</span> (text)
      </div>
      <div class="buttons is-left mt-5">
        <button
          @click="this.showInfo = true"
          class="button is-rounded is-info"
          v-if="!showInfo"
        >
          Show lesson
        </button>
        <button
          @click="this.showInfo = false"
          class="button is-rounded is-info is-light"
          v-else
        >
          Hide lesson
        </button>
      </div>

      <!-- show main lesson content -->
      <div class="content" v-if="showInfo">
        <div class="has-text-link-dark has-text-left title is-6 is-json">
          What the hell is a shell?
        </div>
          <div class="pl-2">
            <div class="block">
              In simple terms, a shell is a computer program that lets you interact with a computer's operating system in a very direct way. 
                Instead of working with a 
                <span class="has-tooltip-arrow has-tooltip-multiline has-tooltip-top"
                    :data-tooltip="'Graphical User Interface'"
                >
                    <span class="has-text-link-dark has-text-weight-bold">
                       GUI,
                    </span>
                </span>
                like the browser you're using right now, the shell lets you interact with the OS and other apps via a 
                <span class="has-tooltip-arrow has-tooltip-multiline has-tooltip-top"
                    :data-tooltip="'Command Line Interface'"
                >
                    <span class="has-text-link-dark has-text-weight-bold">
                       CLI.
                    </span>
                </span> 
                This means that instead of clicking on things, you need to <span class="has-text-dark has-text-weight-bold">run commands</span> to tell the computer what to do. 
            </div>
          <img src="./../assets/shell.png" class="image pl-2" style="height: auto width: 80%">
          <br>
          </div>

        <div class="has-text-link-dark has-text-left title is-6 is-json">
          Working with a computer's network interfaces
        </div>
          <div class="pl-2">
            <div class="block">
              To view the network interfaces available on a 
                <span class="has-tooltip-arrow has-tooltip-multiline has-tooltip-top"
                    :data-tooltip="'in Windows, most of the shell commands are different'"
                >
                    <span class="has-text-link-dark has-text-weight-bold">
                       (Unix)
                    </span>
                </span>
            computer, run <span class="is-family-monospace has-background-light">ip link show</span>
            </div>
            <div class="block mb-5">
              To turn on or off a specific network interface, run <span class="is-family-monospace has-background-light">ip link set dev NAME up|down</span>
            </div>
          </div>

        <div class="has-text-link-dark has-text-left title is-6 is-json">
          Working with a computer's ARP cache
        </div>
          <div class="pl-2">
            <div class="block">
              To view the current ARP cache on the computer, run <span class="is-family-monospace has-background-light">arp</span>
            </div>
            <div class="block">
              To make changes to a specific entry in the ARP cache, run <span class="is-family-monospace has-background-light">arp IP_ADDR MAC_ADDR</span>
            </div>
            <div class="block mb-5"></div>
          </div>

        

        <!-- buttons for showing additional lesson content -->
        <div class="buttons is-left mt-5">
          <button
            @click="this.showAdditionalInformation = true"
            class="button is-rounded"
            v-if="!showAdditionalInformation"
          >
            Tell me more
          </button>
          <button
            @click="this.showAdditionalInformation = false"
            class="button is-rounded"
            v-else
          >
            Show less
          </button>
        </div>
        
        <!-- show additional lesson content -->
        <div class="pl-4" v-if="showAdditionalInformation">
          <div class="has-text-link-dark has-text-left title is-6 is-json">
              Tips on using the shell:
          </div>
          <ul>
            <li>
              although a shell is pretty powerful, it is quite strict on the syntax: you need to 
              <span class="has-text-dark has-text-weight-bold">type the commands in the exact order,</span> 
              including spaces in between
            </li>
            <li>
              with the keys up <span>&#x2191;</span> and down <span>&#x2193;</span> you can go through your
                <span class="has-tooltip-arrow has-tooltip-multiline has-tooltip-top"
                    :data-tooltip="`this is a neat feature if you have a typo in a longer command and don't want to retype it`"
                >
                    <span class="has-text-link-dark has-text-weight-bold">
                       history
                    </span>
                </span>
                of typed commands
            </li>
            <li>
              <span class="is-family-monospace has-background-light">clear</span> - run this command to
                <span class="has-tooltip-arrow has-tooltip-multiline has-tooltip-top"
                    :data-tooltip="`helpful when you have a lot of output you don't need anymore`"
                >
                    <span class="has-text-link-dark has-text-weight-bold">
                       clear the screen
                    </span>
                </span>
            </li>
          </ul>

              
          <div class="has-text-link-dark has-text-left title is-6 is-json">
              More info on selected commands:
          </div>
           <ul>
            <li>
              <span class="is-family-monospace has-background-light">ip link set dev NAME up|down</span> - replace <span class="is-family-monospace has-background-light">NAME</span> with the network interface you want to turn on (<span class="is-family-monospace has-background-light">up</span>) or off (<span class="is-family-monospace has-background-light">down</span>)
            </li>
            <li>
               The name of a network interface usually contains the term 
                <span class="has-tooltip-arrow has-tooltip-multiline has-tooltip-top"
                    :data-tooltip="`'eth' refers to ethernet, think of your LAN card`"
                >
                    <span class="is-family-monospace has-background-light has-text-link-dark has-text-weight-bold">eth</span>
                </span>
                or
                <span class="has-tooltip-arrow has-tooltip-multiline has-tooltip-top"
                    :data-tooltip="'wlan refers to, you guessed it, WLAN'"
                >
                    <span class="is-family-monospace has-background-light has-text-link-dark has-text-weight-bold">
                        wlan</span>
                </span>
            in it. 
            </li>
            <li>
              <span class="is-family-monospace has-background-light">arp -s IP_ADDR MAC_ADDR</span> - run this command to make an ARP entry <span class="has-text-dark has-text-weight-bold">static</span>
            </li>
          </ul>
          <div class="has-text-link-dark has-text-left title is-6 is-json">
              The network topology as a reference:
          </div>
          <img src="./../assets/network.png" class="image p-10" style="height: 50% width: %">
        </div>
      </div>
    </div>
  </div>
</template>

  <script>
export default {
  name: "TextLesson2",
// <img src="../assets/shell.png">
  props: {
    order: {},
  },

  data() {
    return {
      tileNo: "textlesson2",  
      showAdditionalInformation: false,
      showInfo: true,
    };
  },

  methods: {
    proceed() {
      this.showAdditionalInformation = false;
      var nextSection = this.order.indexOf(this.tileNo) + 1;
      console.log(nextSection);
      this.scrollToElement(this.order[nextSection]);
    },

    scrollToElement(id) {
      //const el = document.getElementsByClassName(className)[0];
      const el = document.getElementById(id);
      setTimeout(() => {
        el.scrollIntoView({ behavior: "smooth", alignToTop: true });
      });
    },
  },
};
</script>
