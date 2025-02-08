# VSTAR-ICLR-Supp

## Table of contents
&nbsp;&nbsp;&nbsp;G.1.  [Qualitative results of SOTA T2V models](#SOTA)    
&nbsp;&nbsp;&nbsp;G.2. [Qualitative results of our VSTAR](#VSTAR)   
&nbsp;&nbsp;&nbsp;G.3. [Effect of TAR on longer video generation](#TAR)    
&nbsp;&nbsp;&nbsp;G.4. [Comparison with single-pass methods](#singlepass)   
&nbsp;&nbsp;&nbsp;G.5. [Comparison with multi-pass methods](#multipass)    
&nbsp;&nbsp;&nbsp;G.6. [Ablation of attention regularization matrix](#AblationTAR)   
&nbsp;&nbsp;&nbsp;G.7. [Samples of real videos](#real)     



<div id='SOTA'/>    

## G.1 Qualitative results of SOTA T2V models   

Some recent works, e.g., Open-Sora-Plan and CogVideoX have attempted to reproduce Sora using 3D causal VAE and 3D full attention directly without temporal attention modules. Since these models do not explicitly model the temporal dimension, the proposed strategies are not applicable to them. Nevertheless, we present their qualitative results below, where there are only limited visual changes within the video, consistent with the quantitative results in Table 1.


### G.1.1 Open-Sora-Plan-V1.2

<table class="center">
  <td style="text-align:center;" width="320">"A Ferrari driving on the road, starts to snow"</td>
  <td style="text-align:center;" width="320">"A landscape transitioning from  winter to spring"</td>
  <tr>
  <td><img src=asset/open-sora-plan/ferrari.gif width="320"></td>
  <td><img src=asset/open-sora-plan/landscape_winter_spring.gif width="320"></td>
  <tr>
  <td style="text-align:center;" width="320">"The process of a lava eruption, from smoke emission to lava cooling"</td>
  <td style="text-align:center;" width="320">"A peony starts to bloom, in the field"</td>
  <tr>
  <td><img src=asset/open-sora-plan/lava.gif width="320"></td>
  <td><img src=asset/open-sora-plan/peony.gif width="320"></td>
  <tr>
</table >


### G.1.2 CogVideoX-5B

<table class="center">
  <td style="text-align:center;" width="320">"A Ferrari driving on the road, starts to snow"</td>
  <td style="text-align:center;" width="320">"A landscape transitioning from  winter to spring"</td>
  <tr>
  <td><img src=asset/cogvideox/ferrari.gif width="320"></td>
  <td><img src=asset/cogvideox/landscape.gif width="320"></td>
  <tr>
  <td style="text-align:center;" width="320">"The process of a lava eruption, from smoke emission to lava cooling"</td>
  <td style="text-align:center;" width="320">"A peony starts to bloom, in the field"</td>
  <tr>
  <td><img src=asset/cogvideox/lava.gif width="320"></td>
  <td><img src=asset/cogvideox/peony.gif width="320"></td>
  <tr>
</table >


<div id='VSTAR'/>    

## G.2 Qualitative results of our VSTAR

Below are the GIF versions of Fig. S.5 and Fig. S.6 in the Supplementary Material.

<table class="center">
  <td style="text-align:center;" width="320">"Superman flying in the sky, sunny day becomes a dark rainy day"</td>
  <td style="text-align:center;" width="320">"A young boy becomes an old man, and turns into a young girl"</td>
  <tr>
  <td><img src=asset/VSTAR/superman.gif width="320"></td>
  <td><img src=asset/VSTAR/boy_girl.gif width="320"></td>
  <tr>
  <td style="text-align:center;" width="320">"A day at the beach from dawn till dusk, bird’s-eye view"</td>
  <td style="text-align:center;" width="320">"The seasonal cycle of a lake from frozen winter to autumn"</td>
  <tr>
  <td><img src=asset/VSTAR/beach.gif width="320"></td>
  <td><img src=asset/VSTAR/lake.gif width="320"></td>
  <tr>
  <td style="text-align:center;" width="320">"A mural being painted on a city wall"</td>
  <td style="text-align:center;" width="320">"A caterpillar transforming into a butterfly"</td>
  <tr>
  <td><img src=asset/VSTAR/wall.gif width="320"></td>
  <td><img src=asset/VSTAR/butterfly.gif width="320"></td>
  <tr>
  <td style="text-align:center;" width="320">"A female person's hairstyle changing through the years"</td>
  <td style="text-align:center;" width="320">"A pizza is being made"</td>
  <tr>
  <td><img src=asset/VSTAR/hairstyle.gif width="320"></td>
  <td><img src=asset/VSTAR/pizza.gif width="320"></td>
  <tr>
</table >



<div id='TAR'/>

## G.3 Effect of TAR on longer video generation

For input text prompts that do not require gradual visual appearance changes within the video, VSP is not necessary. However, TAR still plays a crucial role to enable high quality longer video generation (e.g., 64 ~ 128 frames) that better follow the text prompt. Below, we provide visual examples using a **single** text prompt without employing VSP, all generated with the same random seed.

<table class="center">
  <td style="text-align:center;" colspan="2" width="640"> "A corgi walking on the green grass at sunrise" </td>
  <tr>
  <td style="text-align:center;" width="320"> Baseline </td>
  <td style="text-align:center;" width="320"> <b> + TAR </b></td>
  <tr>
  <td><img src=asset/TAR/corgi_VC.gif width="320"></td>
  <td><img src=asset/TAR/corgi_TAR.gif width="320"></td>
  <tr>
  <td style="text-align:center;" colspan="2" width="640"> "A young woman is jogging on the beach" </td>
  <tr>
  <td style="text-align:center;" width="320"> Baseline </td>
  <td style="text-align:center;" width="320"> <b> + TAR </b> </td>
  <tr>
  <td><img src=asset/TAR/jogging_VC.gif width="320"></td>
  <td><img src=asset/TAR/jogging_TAR.gif width="320"></td>
  <tr>
  <td style="text-align:center;" colspan="2" width="640"> "A girl is riding a horse fast on grassland, snowy day" </td>
  <tr>
  <td style="text-align:center;" width="320"> Baseline </td>
  <td style="text-align:center;" width="320"> <b> + TAR </b> </td>
  <tr>
  <td><img src=asset/TAR/horse_VC.gif width="320"></td>
  <td><img src=asset/TAR/horse_TAR.gif width="320"></td>
  <tr>
  <td style="text-align:center;" colspan="2" width="640"> "A man is surfing on waves" </td>
  <tr>
  <td style="text-align:center;" width="320"> Baseline </td>
  <td style="text-align:center;" width="320"> <b> + TAR </b> </td>
  <tr>
  <td><img src=asset/TAR/surfing_VC.gif width="320"></td>
  <td><img src=asset/TAR/surfing_TAR.gif width="320"></td>
  <tr>
</table >



<div id='singlepass'/>    

## G.4 Comparison with single-pass methods
Below are the GIF versions of Fig. S.7 and Fig. S.8 in the Supplementary Material.

<table class="center">
  <td style="text-align:center;" width="10" >  </td>
  <td style="text-align:center;" width="210"> A Ferrari driving on the road, starts to snow
  <td style="text-align:center;" width="210"> A young girl is aging </td>
  <td style="text-align:center;" width="210"> A flower starts to bloom </td>
  <tr>
  <td style="transform: rotate(270deg);" width="5" > ModelScope</td>
  <td><img src=asset/singlepass/drive_ms.gif width="210" height="92"></td>
  <td><img src=asset/singlepass/girl_ms.gif width="210" height="92"></td>
  <td><img src=asset/singlepass/bloom_ms.gif width="210" height="92"></td>
  <tr>
  <td style="text-align:center;transform: rotate(270deg);" width="5" > LaVie </td>
  <td><img src=asset/singlepass/drive_lavie.gif width="210" height="92"></td>
  <td><img src=asset/singlepass/girl_lavie.gif width="210" height="92"></td>
  <td><img src=asset/singlepass/bloom_lavie.gif width="210"></td>
  <tr>
  <td style="text-align:center;transform: rotate(270deg);" width="5" > AnimateDiff </td>
  <td><img src=asset/singlepass/drive_ad.gif width="210" height="92"></td>
  <td><img src=asset/singlepass/girl_ad.gif width="210" height="92"></td>
  <td><img src=asset/singlepass/bloom_ad.gif width="210" height="92"></td>
  <tr>
  <td style="text-align:center;transform: rotate(270deg);" width="5" > VideoCrafter2 </td>
  <td><img src=asset/singlepass/drive_vc.gif width="210" height="92"></td>
  <td><img src=asset/singlepass/girl_vc.gif width="210" height="92"></td>
  <td><img src=asset/singlepass/bloom_vc.gif width="210" height="92"></td>
  <tr>
  <td style="text-align:center;transform: rotate(270deg);" width="5" > <b>VSTAR (Ours)</b> </td>
  <td><img src=asset/singlepass/drive_ours.gif width="210" height="92"></td>
  <td><img src=asset/singlepass/girl_ours.gif width="210" height="92"></td>
  <td><img src=asset/singlepass/bloom_ours.gif width="210" height="92"></td>
  <tr>
</table >



<div id='multipass'/>    

## G.5 Comparison with multi-pass methods
Some prior works such as FreeBloom and FreeNoise attempt to generate long videos by fusing multiple inference runs. In contrast, our VSTAR only requires a single forward pass. FreeBloom is built upon T2I model, thus naturally underperforms T2V models regarding temporal consistency. Due to the multiple inference passes, FreeNoise faces the extra challenge of maintaining coherency of difference runs.  Using the same multi-prompt, our VSTAR shows better consistency and efficiency due to single-pass synthesis enabled by TAR.

<table class="center">
  <td style="text-align:center;" colspan="3" width="210"> 
  "A boy in gray cloths running in the summer; <br>
  &rightarrow; "A man ... running in the autumn"; <br>
  &rightarrow; "An old man .... running in the winter" </td>
  <tr>
  <td style="text-align:center;" width="210" > FreeBloom </td>
  <td style="text-align:center;" width="210"> FreeNoise 
  <td style="text-align:center;" width="210"> <b>VSTAR (Ours)</b> </td>
  <tr>
  <td><img src=asset/multiprompt/freebloom.gif width="210" height="110" ></td>
  <td><img src=asset/multiprompt/freenoise.gif width="210"></td>
  <td><img src=asset/multiprompt/ours.gif width="210"></td>
  <tr>
</table >



<div id='AblationTAR'/>    

## G.6 Ablation of attention regularization matrix
We provide more examples using different attention regularization matrix, using the same text prompt. 
The standard deviation $\sigma$ can control the regularization strength, i.e., a smaller $\sigma$ leading to more visual variations along the temporal dimension.  When applying on both resolution of 64 and 32, the dynamics can be further enhanced. 

<table class="center">
  <td style="text-align:center;" colspan="2" width="320"> "A corgi walking on the green grass at sunrise" </td>
  <tr>
  <td style="text-align:center;" width="320"> None </td>
  <td style="text-align:center;" width="320"> σ<sub>64</sub> = 8 </td>
  <tr>
  <td><img src=asset/ablation_TAR/none.gif width="320"></td>
  <td><img src=asset/ablation_TAR/res64_8.gif width="320"></td>
  <tr>
  <td style="text-align:center;" width="320"> σ<sub>64</sub> = 1  </td>
  <td style="text-align:center;" width="320"> σ<sub>64</sub> = 1, σ<sub>32</sub> = 1 </td>
  <tr>
  <td><img src=asset/ablation_TAR/res64_1.gif width="320"></td>
  <td><img src=asset/ablation_TAR/res64_1_res32_1.gif width="320"></td>
  <tr>
</table >

<div id='real'/>

## G.7 Samples of real videos 
We used DAVIS dataset and videos from the web for experiments and analysis, which are all captured using a single-camera setup. Below are some examples. 

<table class="center">
  <td><img src=asset/real/car_turn.gif width="320"></td>
  <td><img src=asset/real/flower.gif width="320"></td>
  <tr>
  <td><img src=asset/real/sun.gif width="320"></td>
  <td><img src=asset/real/venom.gif width="320"></td>
  <tr>
</table >