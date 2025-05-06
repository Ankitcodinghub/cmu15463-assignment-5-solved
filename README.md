# cmu15463-assignment-5-solved
**TO GET THIS SOLUTION VISIT:** [CMU15463 Assignment 5 Solved](https://www.ankitcodinghub.com/product/cmu15463-assignment-5-solved/)


---

📩 **If you need this solution or have special requests:** **Email:** ankitcoding@gmail.com  
📱 **WhatsApp:** +1 419 877 7882  
📄 **Get a quote instantly using this form:** [Ask Homework Questions](https://www.ankitcodinghub.com/services/ask-homework-questions/)

*We deliver fast, professional, and affordable academic help.*

---

<h2>Description</h2>



<div class="kk-star-ratings kksr-auto kksr-align-center kksr-valign-top" data-payload="{&quot;align&quot;:&quot;center&quot;,&quot;id&quot;:&quot;96265&quot;,&quot;slug&quot;:&quot;default&quot;,&quot;valign&quot;:&quot;top&quot;,&quot;ignore&quot;:&quot;&quot;,&quot;reference&quot;:&quot;auto&quot;,&quot;class&quot;:&quot;&quot;,&quot;count&quot;:&quot;0&quot;,&quot;legendonly&quot;:&quot;&quot;,&quot;readonly&quot;:&quot;&quot;,&quot;score&quot;:&quot;0&quot;,&quot;starsonly&quot;:&quot;&quot;,&quot;best&quot;:&quot;5&quot;,&quot;gap&quot;:&quot;4&quot;,&quot;greet&quot;:&quot;Rate this product&quot;,&quot;legend&quot;:&quot;0\/5 - (0 votes)&quot;,&quot;size&quot;:&quot;24&quot;,&quot;title&quot;:&quot;CMU15463 Assignment 5 Solved&quot;,&quot;width&quot;:&quot;0&quot;,&quot;_legend&quot;:&quot;{score}\/{best} - ({count} {votes})&quot;,&quot;font_factor&quot;:&quot;1.25&quot;}">

<div class="kksr-stars">

<div class="kksr-stars-inactive">
            <div class="kksr-star" data-star="1" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="2" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="3" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="4" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="5" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
    </div>

<div class="kksr-stars-active" style="width: 0px;">
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
    </div>
</div>


<div class="kksr-legend" style="font-size: 19.2px;">
            <span class="kksr-muted">Rate this product</span>
    </div>
    </div>
<div class="page" title="Page 1">
<div class="layoutArea">
<div class="column">
&nbsp;

The purpose of this assignment is to explore photometric stereo as a computational imaging technique for recovering the shape of an object. As we discussed in class, photometric stereo, in its most common form, takes as input images of an object under a fixed orthographic camera and multiple illumination directions. By assuming that the object is Lambertian and the illumination directional, per-pixel albedoes, normals, and eventually depth can be recovered using simple linear algebraic operations.

In the first part of the homework, you will use data captured by us to implement two types of photometric stereo: uncalibrated, where the lighting directions are unknown, and calibrated, where the lighting directions are known. By comparing the two, you will learn about the generalized bas-relief ambiguity [2] that exists in the uncalibrated case. In the second part, you will use uncalibrated photometric stereo to measure the shape of some objects of your choice (up to a generalized bas-relief ambiguity), by capturing images with your own camera. There are also two bonus parts, where you can implement two popular algorithms for resolving the bas-relief ambiguity.

You are strongly encouraged to read the papers by Bellhuemer et al. [2] and Yuille and Snow [5], which discuss the generalized bas-relief ambiguity and uncalibrated photometric stereo. As always, there is a “Hints and Information” section at the end of this document that is likely to help.

1. Photometric stereo

For the first part of the homework, you will use a set of seven images of a face, measured using a near- orthographic camera with fixed viewpoint, and under different illuminations. These images are available as files ./data/input N.tif in the homework ZIP archive, where N = {1, . . . , 7}. These images are linear images, corresponding to RAW files that have been demosaicked and converted to the (linear) sRGB color space.

Initials . Load the seven images in Matlab, convert them to XYZ color space, and extract the luminance channel for each of them. Then, stack the seven luminance channels into a matrix I of size 7 × P , where P is the number of pixels of each luminance channel.

Uncalibrated photometric stereo (15 points). Our goal is to recover a 3 × 1 normal vector n and a scalar albedo a at each pixel of the camera. As we did in class, it will be convenient to consider at each pixel the pseudo-normal b = a · n. We can stack the pseudo-normals for all pixels into a 3 × P matrix B, which we call the pseudo-normal matrix.

Additionally, each of our seven input images is captured under some directional light, described by a 3 × 1 unit-norm vector li. We can stack the seven light vectors into a 3 × 7 matrix L, which we call the light matrix.

Photometric stereo relies on the “n-dot-l” shading model we discussed in class, which is valid under directional light and Lambertian reflectance. Under this model, we can relate the matrices I, L and B through a simple matrix product,

I=LT ·B. (1)

If all of our assumptions are satisfied exactly, the matrix I will have rank equal to exactly 3. In practice, this will not be exactly the case, because of noise and because the n-dot-l shading assumptions are in practice never perfectly accurate. However, we can find a best approximation (in the least-squares sense) by using SVD to recover the best rank-3 decomposition of matrix I. From this decomposition, we can recover estimates for the matrices L and B. In turn, from B we can use normalization to recover estimates for the 1×P albedomatrixAandthe3×P normalmatrixN.

Unfortunately, these estimates are not unique. Let’s call Le and Be the light and pseudo-normal matrices obtained from the above SVD procedure, and let Q be an invertible 3 × 3 matrix. Then, the matrices

</div>
</div>
<div class="layoutArea">
<div class="column">
1

</div>
</div>
</div>
<div class="page" title="Page 2">
<div class="layoutArea">
<div class="column">
LQ = Le · Q and BQ = Q−T Be approximate Equation (1) exactly as well as the original estimates Le and Be.

Use SVD to recover Le and Be, and then convert Be to per-pixel albedoes Ae and normals Ne. Reshape Ae and Ne into single-channel and three-channel images with width and height same as the original image, and show the results. Additionally, visualize the normals as a vector field. (See help for Matlab function quiver for visualizing the normals.) Additionally, select any non-diagonal matrix Q, and visualize the albedo AQ and normals NQ you compute from the corresponding BQ.

Simple rendering (10 points). Use the albedoes and normals you recovered from Be and from BQ to predict what the person would look like (in grayscale) if illuminated from direction l = (0.58, −0.58, −0.58) and from direction l = (−0.58, −0.58, −0.58). Additionally, synthesize images using the normals and albedoes from BQ, after transforming the light vectors by Q. What do you observe when you compare the various images you synthesized?

Enforcing integrability (40 points). As we discussed in class, the per-pixel normals n(x,y) can be related, after appropriate normalization, to the x and y derivatives of the depth image z = f(x,y) cor- responding to the surface of the object we are scanning. Therefore, the true normals are expected to be integrable, as otherwise they would not correspond to a true surface.

Arbitrary invertible transformations Q do not preserve integrability of normal fields. Therefore, we can try to resolve the ambiguity in the normals by trying to find a Q such that the corresponding normal field NQ is integrable. Unfortunately, while enforcing integrability does help remove some of the ambiguity, it is not sufficiet for uniquely determining the true albedoes and normals. As shown by Belhumeur et al. [2], there exists a class of matrices of the form

1 0 0

G=0 1 0, (2)

μνλ

such that, for all μ and ν and for all λ ̸= 0, they are invertible and preserve invertibility. That is, if a normal

field N is integrable, then the transformed field

G−T N (3)

is also integrable! Therefore, by enforcing integrability, we can only hope to recover the per-pixel albedoes and normals up to a matrix of the form G. Put another way, enforcing integrability lets us reduce the degrees of freedom we have from nine (the entries of the original Q) down to three (the μ, ν, λ of G), but not down to zero. Matrices of the form of Equation (2) correspond to the generalized bas-relief (GBR) transformation, so-called because when μ = 0 and ν = 0 this corresponds to the transformation used in bas-relief sculptures to create a perception of 3D shape.

Our goal now is to find a matrix Q such that the corresponding normals NQ are integrable. We will follow the original derivation of Yuille and Snow [5], which solves for the matrix ∆ = QT instead Q. To estimate ∆, first let’s denote as b ̃ = ∆−1be the transformed pseudonormal at each pixel. Then, we can write the integrability constraint at each pixel as:

∂ 􏰊b ̃(2)􏰋 ∂ 􏰊b ̃(1)􏰋

∂x b ̃(3) = ∂y b ̃(3) (4)

⇒ b ̃(3)∂b ̃(2) − b ̃(2)∂b ̃(3) = b ̃(3)∂b ̃(1) − b ̃(1)∂b ̃(3). (5) ∂x ∂x ∂y ∂y

By replacing b ̃ = ∆−1be, and after some manipulation, we arrive at the following linear equation:

􏰈A1 A2 A3 A4 A5 A6􏰉x = 0, (6)

</div>
</div>
<div class="layoutArea">
<div class="column">
2

</div>
</div>
</div>
<div class="page" title="Page 3">
<div class="layoutArea">
<div class="column">
where

</div>
</div>
<div class="layoutArea">
<div class="column">
and x is a 6×1 vector such that,

</div>
<div class="column">
A1 = be(1)∂be (2) − be(2)∂be (1) (7) ∂x ∂x

A2 = be(1)∂be (3) − be(3)∂be (1) (8) ∂x ∂x

A3 = be(2)∂be (3) − be(3)∂be (2) (9) ∂x ∂x

A4 = −be(1)∂be (2) + be(2)∂be (1) (10) ∂y ∂y

A5 = −be(1)∂be (3) + be(3)∂be (1) (11) ∂y ∂y

A6 = −be(2)∂be (3) + be(3)∂be (2), (12) ∂y ∂y

−x(3) x(6) 1

∆=x(2) −x(5) 0, (13)

−x(1) x(4) 0

</div>
</div>
<div class="layoutArea">
<div class="column">
where the fixed third column corresponds to the three degrees of freedom the GBR affords us. You can find the details of the above derivation in Yuille and Snow [5].

You can now compute matrix ∆ by performing the following steps:

<ol>
<li>Form the three-channel “pseudo-normal” image be, and compute its x and y spatial derivatives (use Matlab’s gradient). We recommend applying a small amount of Gaussian filtering to be before using gradient.</li>
<li>Form a homogeneous linear system Ax = 0, by stacking together linear constraints of the form of Equation (6) for all image pixels.</li>
<li>Solve for x, and estimate ∆ from it using Equation (13).</li>
</ol>
Once you have found ∆, apply it to the pseudonormal matrix Be, and then visualize the resulting albedo (show albedo image) and normals (show normal image and normal vector field). Figure 1 shows the expected results.

Figure 1: Uncalibrated photometric stereo results. From left to right, estimated albedo image (times 10), normal image, normal vector field.

Normal integration (10 points). Now that you have a normal field, you can use it to compute a surface

Z = f(x,y). First, compute from the normals the derivatives (∂f , ∂f ). Then, integrate the normals to ∂x ∂y

compute the surface Z = f (x, y).

</div>
</div>
<div class="layoutArea">
<div class="column">
3

</div>
</div>
</div>
<div class="page" title="Page 4">
<div class="layoutArea">
<div class="column">
For the integration, you can experiment with the functions integrate poisson.m and integrate frankot.m provided in the ./src directory in the homework ZIP archive: The first function integrates the derivative vector field by solving the Poisson equation, which is similar to the integration procedure you implemented

in Homework 3. The second function integrates the derivative vector field using a projection method by Frankot and Chellappa [3]. Try both functions, and use the result you like the most.

Visualize the final surface you can reconstructed as both a depth image and a 3D surface. (See help for Matlab function surf.) Figure 2 shows two views of the expected surface.

Figure 2: Uncalibrated photometric stereo results. Two views of the recovered face shape.

Additionally, experiment with GBR transformations G for different values μ,ν,λ, until you find one that produces a reasonably undistorted face surface. Report what GBR you end up using, and show the corresponding albedoes, normals, and 3D surfaces.

Calibrated photometric stereo (20 points). The file ./data/sources.mat in the homework ZIP archive contains the groundtruth light source vectors, in the form of the light matrix L. When the light directions have been calibrated, photometric stereo becomes considerably easier: Given that now both I and L are known, all you have to do is solve the linear system of Equation (1) for the pseudo-normal matrix B.

Solve this linear system to recover per-pixel albedoes and normals. Additionally, perform normal inte- gration as above, to recover the 3D surface z. Visualize the recovered albedoes, normals, and surface as before. Figures 3 and 4 show what you should expect to see. How do these results compare to the results of the uncalibrated case?

Dealing with non-idealities (10 points). Note the poor estimates of the albedo in the area surrounding the nostrils. What is the source of this error? Can you think of a method for finding a better estimate of this information from these seven images.

2. Capture and reconstruct your own shapes

You will now perform uncalibrated photometric stereo using images you capture with your own camera. For this, you should select two objects you want to scan: First, select an object that approximately satisfies the assumptions of photometric stereo (very diffuse reflectance without much/any glossiness, few interreflections and occlusions). Second, select an object that partially violates the assumptions of photometric stereo (e.g., it has a somewhat glossy reflectance, or it has strong convavities).

For each object, capture at least seven images with a fixed camera and different lighting conditions. Make sure to consult the Hints section for information on how to best capture these images. Apply uncalibrated photometric stereo to the sequences of images you capture, and produce a reconstruction of the albedo, normals, and surfaces for each of the two objects. Since your reconstructions will be up to a GBR, you can manually experiment with different GBR transformations until you find the best surface result.

</div>
</div>
<div class="layoutArea">
<div class="column">
4

</div>
</div>
</div>
<div class="page" title="Page 5">
<div class="layoutArea">
<div class="column">
Figure 3: Calibrated photometric stereo results. From left to right, estimated albedo image, normal image, normal vector field.

For each object, show one of the input images you captured, and visualize the albedo, normals, and surface you reconstructed. Additionally, show a rendering of both objects under a new lighting direction of your preference.

3. Bonus: Resolving the GBR ambiguity (100 points)

Following the discovery of the GBR ambiguity, there have been a number of techniques that use different heuristics to try to resolve the ambiguity when performing uncalibrated photometric stereo. Below we mention two that have been particularly successful. For up to 100 points of extra credit (50 points for each method), you can read the corresponding paper, implement their method, and apply it to both the images that came with the homework for Part 1, and the images you captured for Part 2. (You can still get partial credit for incomplete implementations, and for applying the method to just one set of images).

Entropy minimization (50 points). This technique was introduced by Alldrin and Kriegman [1]. The intuition behind it is that many real-world objects have a relatively small number of albedo values (e.g., different parts of the surface are painted with a small number of different colors). Therefore, among all possible GBR transformations, we should prefer the one that reduces the variability of the recovered albedo values. The paper proposes measuring variability using entropy.

Using perspective cameras (50 points). The GBR ambiguity is, in part, a consequence of the fact that we assume an orthographic camera. When the camera we use is perspective, then normals and albedoes can be reconstructed exactly. This was proven by Papadhimitri and Favaro [4], who also show how one can do the reconstruction in this case.

Deliverables

As described on the course website, solutions are submitted through Canvas. Your solution should be an archive (e.g., a ZIP file) that includes the following:

• A PDF report explaining what you did for each problem, including the various visualizations of albe- does, normals, and surfaces, as well as renderings of images, that are requested throughout problems 1 and 2, as well as answers to all questions asked throughout both problems. The report should include any figures and intermediate results that you think may help. Make sure to include explanations of any issues that you may have run into that prevented you from fully solving the assignment, as this will help us determine partial credit.

</div>
</div>
<div class="layoutArea">
<div class="column">
5

</div>
</div>
</div>
<div class="page" title="Page 6">
<div class="section">
<div class="layoutArea">
<div class="column">
Figure 4: Calibrated photometric stereo results. Two views of the recovered face shape.

<ul>
<li>All of your Matlab code, as well as a README file explaining how to use the code.</li>
<li>If you do Bonus Part 3: Your PDF report should include a detailed description of the experiments you performed for either paper. You should also show and compare the albedoes, normals, and surfaces you reconstructed with each method.
Please organize your solution submission using the following file structure:

.zip

.pdf ……………………………………………………………….. The PDF report. src/……………Contains all Matlab M-files and the README file explaining how to use the code. data/………………………………………Contains all image, video, and other data files.

Hints and Information
</li>
</ul>
<ul>
<li>The following code demonstrates one way to use the quiver function.
<pre>           % vect_x is an HxW array of x-components
           % vect_y is an HxW array of y-components
           figure;           % create a new figure
           quiver(vect_x,vect_y,‘.’);
</pre>
<pre>           axis image;  % set unit aspect ratio between x and y axes
           axis ij;     % place origin in top-left corner (like an image)
</pre>
Note that the vector components should be displayed at a suitable resolution. For example, the figure below shows the x-y components of a field of surface normals at three different resolutions. The plot in the middle provides the best summary of the surface shape. The resolution can be adjusted by plotting only every nth element as in quiver(vect x(1:n:end,1:n:end),vect y(1:n:end,1:n:end),‘.’).
</li>
<li>When computing the output radiance from a field of surface normals n(x,y) and albedoes a(x,y) illuminated from direction l, clip negative values using L = max(0, an · l).</li>
<li>The following code demonstrates one way to display a surface in Matlab.</li>
</ul>
</div>
</div>
<div class="layoutArea">
<div class="column">
6

</div>
</div>
</div>
</div>
<div class="page" title="Page 7">
<div class="layoutArea">
<div class="column">
<pre>        % Z is an HxW array of surface depths
        figure;
        s=surf(-Z);  % use the ‘-’ sign since our Z-axis points down
</pre>
<pre>                     % output s is a ‘handle’ for the surface plot
</pre>
<pre>        % adjust axis
        axis image; axis off;
</pre>
<pre>        % change surface properties using SET
        set(s,’facecolor’,[.5 .5 .5],’edgecolor’,’none’);
</pre>
<pre>        % add a light to the axis for visual effect
        l=camlight;
</pre>
<pre>        % enable mouse-guided rotation
        rotate3d on
</pre>
• The quality of your results in problem 2 will critically depend on how well the measuremens you take match the imaging conditions assumed by photometric stereo, namely linearity of measurements, orthographic projection, and directional light. Below are some tips that can help maximize your chances of success.

You should set your camera to fully manual mode, as it is important that exposure time, aperture, focus, and so on do not change as you capture different images. You should rotate the zoom ring on your lens so that you are using the maximum possible focal length of the lens. Once you have done that, you should focus your camera so that the object is sufficiently far away from the front of the lens (at least one-two meters). This is necessary in order for your camera to be approximately orthographic. After focusing, set the aperture to the largest aperture you can have while making sure that all of your object remains within the depth of field. Finally, set your exposure (and, if necessary, ISO) so that the object is well-exposed—no saturated pixels and no very black pixels. Given that you will need to take multiple images without any motion, you should make sure you camera is mounted on a tripod and that it is tethered to your laptop.

Remember that you need linear measurements. Therefore, you should make sure to set the camera to produce RAW images. It should also help to set its white balancing option to AUTO, and its output color space to sRGB. After you have captured your images, you can use dcraw to convert them to demosaiced TIFF, in the same way as you did in Homework 2.

For the lighting, you should use a small light that is far away from the object—at least as far away as the camera. The flash from your mobile phone, or a bright but small desk light would be good light sources. Make sure to capture the object from a sufficiently large set of angles, including lighting from left, right, top, bottom, and front. See the set of images provided for Part 1 to get a sense of the degree of variability you should have. Finally, you should capture your images in a dark room, where there is

</div>
</div>
<div class="layoutArea">
<div class="column">
7

</div>
</div>
</div>
<div class="page" title="Page 8">
<div class="layoutArea">
<div class="column">
no (or at least, very little) ambient light.

Credits

A lot of inspiration for this assignment, as well as parts of the write-up and the data for Part 1, came from the computer vision course offered by Todd Zickler at Harvard.

References

<ol>
<li>[1] &nbsp;N. G. Alldrin, S. P. Mallick, and D. J. Kriegman. Resolving the generalized bas-relief ambiguity by entropy minimization. In Computer Vision and Pattern Recognition, 2007. CVPR’07. IEEE Conference on, pages 1–7. IEEE, 2007.</li>
<li>[2] &nbsp;P. N. Belhumeur, D. J. Kriegman, and A. L. Yuille. The bas-relief ambiguity. International journal of computer vision, 35(1):33–44, 1999.</li>
<li>[3] &nbsp;R. Frankot and R. Chellappa. A method for enforcing integrability in shape from shading algorithms. IEEE Transactions on Pattern Analysis &amp; Machine Intelligence, (4):439–451, 1988.</li>
<li>[4] &nbsp;T. Papadhimitri and P. Favaro. A new perspective on uncalibrated photometric stereo. In Proceedings of the IEEE Conference on Computer Vision and Pattern Recognition, pages 1474–1481, 2013.</li>
<li>[5] &nbsp;A. Yuille and D. Snow. Shape and albedo from multiple images using integrability. In Computer Vision and Pattern Recognition, 1997. Proceedings., 1997 IEEE Computer Society Conference on, pages 158– 164. IEEE, 1997.</li>
</ol>
</div>
</div>
<div class="layoutArea">
<div class="column">
8

</div>
</div>
</div>
