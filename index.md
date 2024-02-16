


## Overview
<p align="justify">
Controllable text-to-speech (TTS) aims to achieve flexible and accurate control, 
synthesizing speech across various domains. 
Several recent works adopting natural language descriptions to control speech attributes has gained 
much attention. However, achieving accurate timbre control when utilizing text to manipulate speech 
style poses significant challenges. In light of this, 
we propose VS-TTS, a multi-modal prompt speech synthesis system that allows user-friendly control 
over voice styles while maintain speaker identity. 
Specifically, 1) We present the baseline model for the VS-TTS task, providing detailed descriptions of dataset preprocessing. 
2) We employ a BERT-based text prompt encoder to extract a fixed-length speaking-style-correlated hidden. For speaker prompt, we leverage a multi-stream transformer encoder to learn diverse speaker attributes from multiple views and thus improve speaker similarity. 3) To improve style expressiveness and alleviate one-to-many problem, we introduce a diffusion-based Variation Enhance Network to provide finer grained additional variability information as a supplement for those acoustic features not coverage in natural language prompts. Our extensive evaluations in audiobook dataset (LibriTTS) and multi-corpus emotional datasets demonstrate that VS-TTS outperforms baseline models in terms of style controllability and speaker similarity.
</p>

## Model Architecture
<table>
    <tr>
        <td ><center><img src="assets/image/figure1.png"/> </center></td>
    </tr>
</table>

<p align="center">Figure.1 The overall architecture of VS-TTS.</p>

## LibriTTS seen test set
<script>
function pauseOthers(ele) {
    $("audio").not(ele).each(function (index, audio) {audio.pause();});
}
</script>

<style>
.main-content table {
    display: inline-table;
}
table {
    table-layout:fixed;
    width: 100%;
    overflow: hidden;
}
#player{
    width: 100%;
}
</style>
<p>&nbsp;</p> 
1.GRACE INVOLVES THE REMISSION OF SINS PEACE AND A HAPPY CONSCIENCE<br>
<table>
    <tr>
        <th> GT</th>
        <th> GT Codec</th>
        <th> YourTTS</th>
        <th> Valle</th>
        <th> MegaTTS</th>
        <th> MobileSpeech</th>
    </tr>
    <tr>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/1/gtexample.wav" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/1/gtcodec.wav" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/1/yourtts.wav" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/1/valle.wav" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/1/megatts.wav" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/1/mobilespeech.wav" type="audio/mpeg"></audio> </th>
    </tr>	
</table>

<p>&nbsp;</p> 
2.OVER THE TRACK LINED CITY STREET THE YOUNG MEN THE GRINNING MEN PASS<br>
<table>
    <tr>
        <th> GT</th>
        <th> GT Codec</th>
        <th> YourTTS</th>
        <th> Valle</th>
        <th> MegaTTS</th>
        <th> MobileSpeech</th>
    </tr>
    <tr>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/2/gtexample.wav" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/2/gtcodec.wav" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/2/yourtts.wav" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/2/valle.wav" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/2/megatts.wav" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/2/mobilespeech.wav" type="audio/mpeg"></audio> </th>
    </tr>	
</table>

<p>&nbsp;</p> 
3.FAIRVIEW WAS TWELVE MILES AWAY BUT BY TEN O'CLOCK THEY DREW UP AT THE COUNTY JAIL<br>
<table>
    <tr>
        <th> GT</th>
        <th> GT Codec</th>
        <th> YourTTS</th>
        <th> Valle</th>
        <th> MegaTTS</th>
        <th> MobileSpeech</th>
    </tr>
    <tr>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/3/gtexample.wav" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/3/gtcodec.wav" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/3/yourtts.wav" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/3/valle.wav" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/3/megatts.wav" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/3/mobilespeech.wav" type="audio/mpeg"></audio> </th>
    </tr>	
</table>

<p>&nbsp;</p> 
4.THE JOHN BRIGHT IS ARMED WITH A WEAPON OF GREAT POWER AGAINST WHICH IT IS IMPOSSIBLE THAT THE PEOPLE OF BRITANNULA SHOULD PREVAIL<br>
<table>
    <tr>
        <th> GT</th>
        <th> GT Codec</th>
        <th> YourTTS</th>
        <th> Valle</th>
        <th> MegaTTS</th>
        <th> MobileSpeech</th>
    </tr>
    <tr>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/4/gtexample.wav" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/4/gtcodec.wav" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/4/yourtts.wav" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/4/valle.wav" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/4/megatts.wav" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/4/mobilespeech.wav" type="audio/mpeg"></audio> </th>
    </tr>	
</table>

<p>&nbsp;</p> 
5.IT IS NECESSARY THEREFORE THAT HE SHOULD COMPLY THE KING FROWNED<br>
<table>
    <tr>
        <th> GT</th>
        <th> GT Codec</th>
        <th> YourTTS</th>
        <th> Valle</th>
        <th> MegaTTS</th>
        <th> MobileSpeech</th>
    </tr>
    <tr>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/5/gtexample.wav" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/5/gtcodec.wav" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/5/yourtts.wav" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/5/valle.wav" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/5/megatts.wav" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/5/mobilespeech.wav" type="audio/mpeg"></audio> </th>
    </tr>	
</table>

<p>&nbsp;</p> 
6.AT THE SUDDEN SHARP STING OF IT THE GREAT BIRD TURNED HIS HEAD AND NOTICED FOR THE FIRST TIME THE FISHERMAN STANDING ON THE BANK<br>
<table>
    <tr>
        <th> GT</th>
        <th> GT Codec</th>
        <th> YourTTS</th>
        <th> Valle</th>
        <th> MegaTTS</th>
        <th> MobileSpeech</th>
    </tr>
    <tr>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/6/gtexample.wav" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/6/gtcodec.wav" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/6/yourtts.wav" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/6/valle.wav" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/6/megatts.wav" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/6/mobilespeech.wav" type="audio/mpeg"></audio> </th>
    </tr>	
</table>

## LibriTTS unseen test set
<p>&nbsp;</p> 
7.A STAGE MEAL IS POPULAR BECAUSE IT PROVES TO THE AUDIENCE THAT THE ACTORS EVEN WHEN CALLED CHARLES HAWTREY OR OWEN NARES ARE REAL PEOPLE JUST LIKE YOU AND ME<br>
<table>
    <tr>
        <th> GT</th>
        <th> GT Codec</th>
        <th> YourTTS</th>
        <th> Valle</th>
        <th> MegaTTS</th>
        <th> MobileSpeech</th>
    </tr>
    <tr>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/7/gtexample.wav" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/7/gtcodec.wav" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/7/yourtts.wav" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/7/valle.wav" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/7/megatts.wav" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/7/mobilespeech.wav" type="audio/mpeg"></audio> </th>
    </tr>	
</table>

<p>&nbsp;</p> 
8.WARRENTON SPOKE THUS WITH SIGNIFICANCE TO SHOW ROBIN THAT HE WAS NOT TO THINK GEOFFREY'S CLAIMS TO THE ESTATE WOULD BE PASSED BY<br>
<table>
    <tr>
        <th> GT</th>
        <th> GT Codec</th>
        <th> YourTTS</th>
        <th> Valle</th>
        <th> MegaTTS</th>
        <th> MobileSpeech</th>
    </tr>
    <tr>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/8/gtexample.wav" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/8/gtcodec.wav" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/8/yourtts.wav" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/8/valle.wav" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/8/megatts.wav" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/8/mobilespeech.wav" type="audio/mpeg"></audio> </th>
    </tr>	
</table>

<p>&nbsp;</p> 
9.TAKING ADVANTAGE OF THIS THE SQUIRE'S FEW MEN REDOUBLED THEIR EFFORTS AND ENCOURAGED BY ROBIN'S AND THE LITTLE STROLLER'S CRIES FOUGHT THEIR WAY TO HIM<br>
<table>
    <tr>
        <th> GT</th>
        <th> GT Codec</th>
        <th> YourTTS</th>
        <th> Valle</th>
        <th> MegaTTS</th>
        <th> MobileSpeech</th>
    </tr>
    <tr>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/9/gtexample.wav" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/9/gtcodec.wav" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/9/yourtts.wav" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/9/valle.wav" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/9/megatts.wav" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/9/mobilespeech.wav" type="audio/mpeg"></audio> </th>
    </tr>	
</table>

<p>&nbsp;</p> 
10.HE CRIED IN HIGH DUDGEON JUST AS IF HE OWNED THE WHOLE OF THE PEPPERS AND COULD DISPOSE OF THEM ALL TO SUIT HIS FANCY<br>
<table>
    <tr>
        <th> GT</th>
        <th> GT Codec</th>
        <th> YourTTS</th>
        <th> Valle</th>
        <th> MegaTTS</th>
        <th> MobileSpeech</th>
    </tr>
    <tr>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/10/gtexample.wav" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/10/gtcodec.wav" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/10/yourtts.wav" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/10/valle.wav" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/10/megatts.wav" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/10/mobilespeech.wav" type="audio/mpeg"></audio> </th>
    </tr>	
</table>

<p>&nbsp;</p> 
11.FRANK READ ENGLISH SLOWLY AND THE MORE HE READ ABOUT THIS DIVORCE CASE THE ANGRIER HE GREW<br>
<table>
    <tr>
        <th> GT</th>
        <th> GT Codec</th>
        <th> YourTTS</th>
        <th> Valle</th>
        <th> MegaTTS</th>
        <th> MobileSpeech</th>
    </tr>
    <tr>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/11/gtexample.wav" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/11/gtcodec.wav" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/11/yourtts.wav" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/11/valle.wav" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/11/megatts.wav" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/11/mobilespeech.wav" type="audio/mpeg"></audio> </th>
    </tr>	
</table>

## Emotional Speech unseen test set
<p>&nbsp;</p> 
12.THAT'S NOT MUCH OF A JOB FOR AN ATHLETE HERE I'VE BEEN TO TOWN AND BACK<br>
<table>
    <tr>
        <th> GT</th>
        <th> GT Codec</th>
        <th> YourTTS</th>
        <th> Valle</th>
        <th> MegaTTS</th>
        <th> MobileSpeech</th>
    </tr>
    <tr>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/12/gtexample.wav" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/12/gtcodec.wav" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/12/yourtts.wav" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/12/valle.wav" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/12/megatts.wav" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/12/mobilespeech.wav" type="audio/mpeg"></audio> </th>
    </tr>	
</table>

<p>&nbsp;</p> 
13.BUT THE WINDOWS ARE PATCHED WITH WOODEN PANES AND THE DOOR I THINK IS LIKE THE GATE IT IS NEVER OPENED<br>
<table>
    <tr>
        <th> GT</th>
        <th> GT Codec</th>
        <th> YourTTS</th>
        <th> Valle</th>
        <th> MegaTTS</th>
        <th> MobileSpeech</th>
    </tr>
    <tr>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/13/gtexample.wav" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/13/gtcodec.wav" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/13/yourtts.wav" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/13/valle.wav" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/13/megatts.wav" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/13/mobilespeech.wav" type="audio/mpeg"></audio> </th>
    </tr>	
</table>

<p>&nbsp;</p> 
14.IT IS SO MADE THAT EVERYWHERE WE FEEL THE SENSE OF PUNISHMENT<br>
<table>
    <tr>
        <th> GT</th>
        <th> GT Codec</th>
        <th> YourTTS</th>
        <th> Valle</th>
        <th> MegaTTS</th>
        <th> MobileSpeech</th>
    </tr>
    <tr>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/14/gtexample.wav" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/14/gtcodec.wav" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/14/yourtts.wav" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/14/valle.wav" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/14/megatts.wav" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/14/mobilespeech.wav" type="audio/mpeg"></audio> </th>
    </tr>	
</table>

<p>&nbsp;</p> 
15.NO ONE WOULD DISTURB THEIR LITTLE HOUSE EVEN IF ANYONE CAME SO FAR INTO THE THICK FOREST WHILE THEY WERE GONE<br>
<table>
    <tr>
        <th> GT</th>
        <th> GT Codec</th>
        <th> YourTTS</th>
        <th> Valle</th>
        <th> MegaTTS</th>
        <th> MobileSpeech</th>
    </tr>
    <tr>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/15/gtexample.wav" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/15/gtcodec.wav" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/15/yourtts.wav" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/15/valle.wav" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/15/megatts.wav" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/15/mobilespeech.wav" type="audio/mpeg"></audio> </th>
    </tr>	
</table>

<p>&nbsp;</p> 
16.WE ARE TRAVELING REPLIED OJO AND WE STOPPED AT YOUR HOUSE JUST TO REST AND REFRESH OURSELVES<br>
<table>
    <tr>
        <th> GT</th>
        <th> GT Codec</th>
        <th> YourTTS</th>
        <th> Valle</th>
        <th> MegaTTS</th>
        <th> MobileSpeech</th>
    </tr>
    <tr>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/16/gtexample.wav" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/16/gtcodec.wav" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/16/yourtts.wav" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/16/valle.wav" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/16/megatts.wav" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/16/mobilespeech.wav" type="audio/mpeg"></audio> </th>
    </tr>	
</table>

<p>&nbsp;</p> 
17.DID EVER ANYBODY SEE THE LIKE SCREAMED MISSUS POYSER RUNNING TOWARDS THE TABLE WHEN HER EYE HAD FALLEN ON THE BLUE STREAM<br>
<table>
    <tr>
        <th> GT</th>
        <th> GT Codec</th>
        <th> YourTTS</th>
        <th> Valle</th>
        <th> MegaTTS</th>
        <th> MobileSpeech</th>
    </tr>
    <tr>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/17/gtexample.wav" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/17/gtcodec.wav" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/17/yourtts.wav" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/17/valle.wav" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/17/megatts.wav" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/17/mobilespeech.wav" type="audio/mpeg"></audio> </th>
    </tr>	
</table>

<p>&nbsp;</p> 
18.SOMEONE ELSE TOLD A STORY NOT PARTICULARLY EFFECTIVE WHICH I SAW HE WAS NOT FOLLOWING<br>
<table>
    <tr>
        <th> GT</th>
        <th> GT Codec</th>
        <th> YourTTS</th>
        <th> Valle</th>
        <th> MegaTTS</th>
        <th> MobileSpeech</th>
    </tr>
    <tr>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/18/gtexample.wav" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/18/gtcodec.wav" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/18/yourtts.wav" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/18/valle.wav" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/18/megatts.wav" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/18/mobilespeech.wav" type="audio/mpeg"></audio> </th>
    </tr>	
</table>

<p>&nbsp;</p> 
19.THE LEADERS OF THE CONSPIRACY BECAME DISTRUSTFUL OF THEIR POWER TO CRUSH THE TOWN<br>
<table>
    <tr>
        <th> GT</th>
        <th> GT Codec</th>
        <th> YourTTS</th>
        <th> Valle</th>
        <th> MegaTTS</th>
        <th> MobileSpeech</th>
    </tr>
    <tr>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/19/gtexample.wav" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/19/gtcodec.wav" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/19/yourtts.wav" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/19/valle.wav" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/19/megatts.wav" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/19/mobilespeech.wav" type="audio/mpeg"></audio> </th>
    </tr>	
</table>

<p>&nbsp;</p> 
20.THERE WAS SOMETHING IN HIS AIR AND MANNER THAT BETRAYED TO THE SCOUT THE UTTER CONFUSION OF THE STATE OF HIS MIND<br>
<table>
    <tr>
        <th> GT</th>
        <th> GT Codec</th>
        <th> YourTTS</th>
        <th> Valle</th>
        <th> MegaTTS</th>
        <th> MobileSpeech</th>
    </tr>
    <tr>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/20/gtexample.wav" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/20/gtcodec.wav" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/20/yourtts.wav" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/20/valle.wav" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/20/megatts.wav" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/20/mobilespeech.wav" type="audio/mpeg"></audio> </th>
    </tr>	
</table>

<p>&nbsp;</p> 
21.AS SOON AS THESE DISPOSITIONS WERE MADE THE SCOUT TURNED TO DAVID AND GAVE HIM HIS PARTING INSTRUCTIONS<br>
<table>
    <tr>
        <th> GT</th>
        <th> GT Codec</th>
        <th> YourTTS</th>
        <th> Valle</th>
        <th> MegaTTS</th>
        <th> MobileSpeech</th>
    </tr>
    <tr>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/21/gtexample.wav" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/21/gtcodec.wav" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/21/yourtts.wav" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/21/valle.wav" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/21/megatts.wav" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/21/mobilespeech.wav" type="audio/mpeg"></audio> </th>
    </tr>	
</table>

<p>&nbsp;</p> 
22.LET US RETRACE OUR STEPS AND EXAMINE AS WE GO WITH KEENER EYES<br>
<table>
    <tr>
        <th> GT</th>
        <th> GT Codec</th>
        <th> YourTTS</th>
        <th> Valle</th>
        <th> MegaTTS</th>
        <th> MobileSpeech</th>
    </tr>
    <tr>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/22/gtexample.wav" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/22/gtcodec.wav" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/22/yourtts.wav" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/22/valle.wav" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/22/megatts.wav" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/22/mobilespeech.wav" type="audio/mpeg"></audio> </th>
    </tr>	
</table>

<p>&nbsp;</p> 
23.IS THE ATMOSPHERIC CONDITION HAVING ONCE REACHED THIS DENSITY TO BECOME FINAL<br>
<table>
    <tr>
        <th> GT</th>
        <th> GT Codec</th>
        <th> YourTTS</th>
        <th> Valle</th>
        <th> MegaTTS</th>
        <th> MobileSpeech</th>
    </tr>
    <tr>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/23/gtexample.wav" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/23/gtcodec.wav" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/23/yourtts.wav" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/23/valle.wav" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/23/megatts.wav" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/23/mobilespeech.wav" type="audio/mpeg"></audio> </th>
    </tr>	
</table>

<p>&nbsp;</p> 
24.ON FRIDAY CONFESSION WILL BE HEARD ALL THE AFTERNOON AFTER BEADS<br>
<table>
    <tr>
        <th> GT</th>
        <th> GT Codec</th>
        <th> YourTTS</th>
        <th> Valle</th>
        <th> MegaTTS</th>
        <th> MobileSpeech</th>
    </tr>
    <tr>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/24/gtexample.wav" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/24/gtcodec.wav" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/24/yourtts.wav" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/24/valle.wav" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/24/megatts.wav" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/24/mobilespeech.wav" type="audio/mpeg"></audio> </th>
    </tr>	
</table>

<p>&nbsp;</p> 
25.HE STOOD STILL IN DEFERENCE TO THEIR CALLS AND PARRIED THEIR BANTER WITH EASY WORDS<br>
<table>
    <tr>
        <th> GT</th>
        <th> GT Codec</th>
        <th> YourTTS</th>
        <th> Valle</th>
        <th> MegaTTS</th>
        <th> MobileSpeech</th>
    </tr>
    <tr>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/25/gtexample.wav" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/25/gtcodec.wav" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/25/yourtts.wav" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/25/valle.wav" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/25/megatts.wav" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/25/mobilespeech.wav" type="audio/mpeg"></audio> </th>
    </tr>	
</table>

<p>&nbsp;</p> 
26.THIS DIFFERENTIATION IS FURTHERED BY THE INHERITANCE OF WEALTH AND THE CONSEQUENT INHERITANCE OF GENTILITY<br>
<table>
    <tr>
        <th> GT</th>
        <th> GT Codec</th>
        <th> YourTTS</th>
        <th> Valle</th>
        <th> MegaTTS</th>
        <th> MobileSpeech</th>
    </tr>
    <tr>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/26/gtexample.wav" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/26/gtcodec.wav" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/26/yourtts.wav" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/26/valle.wav" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/26/megatts.wav" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/26/mobilespeech.wav" type="audio/mpeg"></audio> </th>
    </tr>	
</table>

<p>&nbsp;</p> 
27.HE COULD HARDLY STAND STILL SO GREAT WAS HIS MENTAL AGITATION AND HE RAN TOWARDS HOLMES WITH TWO EAGER HANDS OUTSTRETCHED THANK HEAVEN THAT YOU HAVE COME<br>
<table>
    <tr>
        <th> GT</th>
        <th> GT Codec</th>
        <th> YourTTS</th>
        <th> Valle</th>
        <th> MegaTTS</th>
        <th> MobileSpeech</th>
    </tr>
    <tr>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/27/gtexample.wav" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/27/gtcodec.wav" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/27/yourtts.wav" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/27/valle.wav" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/27/megatts.wav" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/27/mobilespeech.wav" type="audio/mpeg"></audio> </th>
    </tr>	
</table>

<p>&nbsp;</p> 
28.BARTLEY LEANED OVER HER SHOULDER WITHOUT TOUCHING HER AND WHISPERED IN HER EAR YOU ARE GIVING ME A CHANCE YES<br>
<table>
    <tr>
        <th> GT</th>
        <th> GT Codec</th>
        <th> YourTTS</th>
        <th> Valle</th>
        <th> MegaTTS</th>
        <th> MobileSpeech</th>
    </tr>
    <tr>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/28/gtexample.wav" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/28/gtcodec.wav" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/28/yourtts.wav" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/28/valle.wav" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/28/megatts.wav" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/28/mobilespeech.wav" type="audio/mpeg"></audio> </th>
    </tr>	
</table>

<p>&nbsp;</p> 
29.BUT THE REAL SIGNIFICANCE AND COMFORT OF THE WORDS FOR OUR SINS IS LOST UPON THEM<br>
<table>
    <tr>
        <th> GT</th>
        <th> GT Codec</th>
        <th> YourTTS</th>
        <th> Valle</th>
        <th> MegaTTS</th>
        <th> MobileSpeech</th>
    </tr>
    <tr>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/29/gtexample.wav" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/29/gtcodec.wav" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/29/yourtts.wav" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/29/valle.wav" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/29/megatts.wav" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/29/mobilespeech.wav" type="audio/mpeg"></audio> </th>
    </tr>	
</table>

<p>&nbsp;</p> 
30.ANYHOW WE'LL LEAVE INSTRUCTIONS TO SHIP THE WHOLE MENAGERIE TO FRANCE<br>
<table>
    <tr>
        <th> GT</th>
        <th> GT Codec</th>
        <th> YourTTS</th>
        <th> Valle</th>
        <th> MegaTTS</th>
        <th> MobileSpeech</th>
    </tr>
    <tr>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/30/gtexample.wav" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/30/gtcodec.wav" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/30/yourtts.wav" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/30/valle.wav" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/30/megatts.wav" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/30/mobilespeech.wav" type="audio/mpeg"></audio> </th>
    </tr>	
</table>

<p>&nbsp;</p> 
31.KESWICK MARCH TWENTY SECOND EIGHTEEN THIRTY SEVEN DEAR MADAM<br>
<table>
    <tr>
        <th> GT</th>
        <th> GT Codec</th>
        <th> YourTTS</th>
        <th> Valle</th>
        <th> MegaTTS</th>
        <th> MobileSpeech</th>
    </tr>
    <tr>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/31/gtexample.wav" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/31/gtcodec.wav" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/31/yourtts.wav" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/31/valle.wav" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/31/megatts.wav" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/31/mobilespeech.wav" type="audio/mpeg"></audio> </th>
    </tr>	
</table>

<p>&nbsp;</p> 
32.VAST IMPORTANCE AND INFLUENCE OF THIS MENTAL FURNISHING<br>
<table>
    <tr>
        <th> GT</th>
        <th> GT Codec</th>
        <th> YourTTS</th>
        <th> Valle</th>
        <th> MegaTTS</th>
        <th> MobileSpeech</th>
    </tr>
    <tr>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/32/gtexample.wav" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/32/gtcodec.wav" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/32/yourtts.wav" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/32/valle.wav" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/32/megatts.wav" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/32/mobilespeech.wav" type="audio/mpeg"></audio> </th>
    </tr>	
</table>

<p>&nbsp;</p> 
33.HE DARTED THROUGH THE TREES AND PAUSED A TALL MAN STRONGLY BUT SLIMLY MADE<br>
<table>
    <tr>
        <th> GT</th>
        <th> GT Codec</th>
        <th> YourTTS</th>
        <th> Valle</th>
        <th> MegaTTS</th>
        <th> MobileSpeech</th>
    </tr>
    <tr>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/33/gtexample.wav" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/33/gtcodec.wav" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/33/yourtts.wav" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/33/valle.wav" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/33/megatts.wav" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/33/mobilespeech.wav" type="audio/mpeg"></audio> </th>
    </tr>	
</table>

<p>&nbsp;</p> 
34.ALAS I HAVE GRIEVED SO I AM HARD TO LOVE<br>
<table>
    <tr>
        <th> GT</th>
        <th> GT Codec</th>
        <th> YourTTS</th>
        <th> Valle</th>
        <th> MegaTTS</th>
        <th> MobileSpeech</th>
    </tr>
    <tr>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/34/gtexample.wav" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/34/gtcodec.wav" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/34/yourtts.wav" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/34/valle.wav" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/34/megatts.wav" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/34/mobilespeech.wav" type="audio/mpeg"></audio> </th>
    </tr>	
</table>

<p>&nbsp;</p> 
35.IN PERSON WELCOME ABOARD PROFESSOR YOUR CABIN IS WAITING FOR YOU<br>
<table>
    <tr>
        <th> GT</th>
        <th> GT Codec</th>
        <th> YourTTS</th>
        <th> Valle</th>
        <th> MegaTTS</th>
        <th> MobileSpeech</th>
    </tr>
    <tr>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/35/gtexample.wav" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/35/gtcodec.wav" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/35/yourtts.wav" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/35/valle.wav" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/35/megatts.wav" type="audio/mpeg"></audio> </th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/waves/35/mobilespeech.wav" type="audio/mpeg"></audio> </th>
    </tr>	
</table>

## Chinese Speech Samples

<p>&nbsp;</p> 
1.今后我们要加强和发达地区的交流与合作，共同开发，尽快把内蒙古经济搞上去。<br>
<table>
    <tr>
        <th> MobileSpeech</th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/spk_80064_000110_infer.wav" type="audio/mpeg"></audio> </th>
    </tr>
</table>

<p>&nbsp;</p> 
2.据了解，天津市今年粮食种植面积达六百六十五万亩，预计全年粮食总产量可达二十点七五亿公斤，比去年提高百分之九。<br>
<table>
    <tr>
        <th> MobileSpeech</th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/good_spk_80064_000000.wav" type="audio/mpeg"></audio> </th>
    </tr>
</table>

<p>&nbsp;</p> 
3.财产所有权转移了，其风险责任也随之转移。<br>
<table>
    <tr>
        <th> MobileSpeech</th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/spk_80065_000196_infer.wav" type="audio/mpeg"></audio> </th>
    </tr>
</table>

<p>&nbsp;</p> 
4.我们几个人你看看我，我看看你，一筹莫展。<br>
<table>
    <tr>
        <th> MobileSpeech</th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/spk_80069_000051_infer.wav" type="audio/mpeg"></audio> </th>
    </tr>
</table>

<p>&nbsp;</p> 
5.达成意向的有二十四个单位，涉及十九个项目，两百九十二名运动员。<br>
<table>
    <tr>
        <th> MobileSpeech</th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/spk_80073_000161_infer.wav" type="audio/mpeg"></audio> </th>
    </tr>
</table>

<p>&nbsp;</p> 
6.图为喇叭哥在用吼声执法。<br>
<table>
    <tr>
        <th> MobileSpeech</th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/spk_80074_000164_infer.wav" type="audio/mpeg"></audio> </th>
    </tr>
</table>

<p>&nbsp;</p> 
7.而是为了调整产业结构和所有制结构，更好地发展社会生产力。<br>
<table>
    <tr>
        <th> MobileSpeech</th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/good_spk_80067_000068.wav" type="audio/mpeg"></audio> </th>
    </tr>
</table>

<p>&nbsp;</p> 
8.有位长者被挤得东歪西倒，手上还紧紧拖着一只折叠的简易行李车，车上捆着两三个大行李袋。<br>
<table>
    <tr>
        <th> MobileSpeech</th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/good_spk_80070_000029.wav" type="audio/mpeg"></audio> </th>
    </tr>
</table>

<p>&nbsp;</p> 
9.女人渐渐爱上了老汉，这爱滋润老汉干枯的生命变得鲜活起来，不料，秋收打场过后，女人却出于无奈悄悄离开了老汉。<br>
<table>
    <tr>
        <th> MobileSpeech</th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/good_spk_80065_000002.wav" type="audio/mpeg"></audio> </th>
    </tr>
</table>

<p>&nbsp;</p> 
10.往前走，家庭皮鞋作坊里机声踏踏，鱼塘上阳光布洒每个家庭，每座小院，都成了农工们各显神通的舞台。<br>
<table>
    <tr>
        <th> MobileSpeech</th>
        <th> <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audios/spk_80079_000014_infer.wav" type="audio/mpeg"></audio> </th>
    </tr>
</table>
