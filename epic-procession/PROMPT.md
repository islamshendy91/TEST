# Epic Procession: cinematic shot prompt pack

A ready-to-use prompt pack for a reference-driven image/video model (Veo, Sora,
Kling, Runway Gen-4 References, Higgsfield, Midjourney `--cref`, etc.).

## 1. Reference photos to upload

Upload these as character / face references. The originals are not stored in
this repo.

| Use | Photo | Why |
|---|---|---|
| Primary face | Grey blazer, stone wall, frontal smile | Sharpest, evenly lit, straight-on |
| Secondary face | Black shirt over white tee, neutral expression, office | Neutral expression to match the tired mood |
| Angle | Black tee, office ceiling light, 3/4 angle | Gives the model the side of the face |
| Body / outfit | Black tee + light jeans, mirror selfie at the lockers | Build, height and outfit proportions |

Every reference shows glasses. Because the shot has none, keep "no glasses"
in the prompt **and** in the negative prompt, or the model will copy them.

## 2. Character description (paste with every prompt)

> Man in his mid-30s, olive/tan skin, short dark curly hair with faded
> sides, thick dark mustache joined to a short trimmed beard and goatee with
> a little grey in it, medium-heavy build, broad shoulders. **No glasses.**
> Plain black crew-neck t-shirt, wide-leg light-blue washed jeans, dark
> boots. Clothes covered in dust.

## 3. Main prompt (video, 16:9)

```
Cinematic low-angle tracking shot, camera dollying backward in front of the subject.
A man [CHARACTER DESCRIPTION] walks slowly toward the camera down the middle of an
empty, abandoned city road. Heavy grey overcast sky, faint smoke haze drifting
across the street, scattered debris and dust on the asphalt.

A large dark-red lion with a heavy dark mane walks at his right side, matching
his pace. In front of him, leading the way a few metres ahead, walk a black wolf
and a black tiger side by side. A large eagle glides low overhead, wings spread.
Close behind him follow two tall shadowy knights in dark, scratched and dented
plate armour, faces hidden by helmets.

Everyone looks exhausted and battle-worn: dusty, slow steady steps, heads
slightly lowered, eyes forward, quiet determination. The man's expression is
calm and tired, not smiling.

Slow motion, 24fps film look, anamorphic lens, shallow depth of field, subtle
film grain, moody desaturated teal-grey color grade with muted warm skin tones,
soft diffused light, volumetric haze, epic film look. 16:9, 8 seconds.
```

### Negative prompt

```
glasses, eyeglasses, sunglasses, smiling, cartoon, anime, CGI-looking animals,
extra limbs, extra animals, crowds, cars, bright sunlight, saturated colours,
text, watermark, distorted face, face morphing, different person
```

## 4. Still image version (key art)

```
Epic movie still, low-angle wide shot, 16:9. [CHARACTER DESCRIPTION] walking
toward the camera down an empty overcast city road, faint smoke haze. A dark-red
lion walks beside him; a black wolf and a black tiger lead in front; an eagle
glides above with spread wings; two shadowy armoured knights follow behind.
All tired and battle-worn, dusty, slow steady steps. Desaturated moody color
grade, anamorphic lens, shallow depth of field, film grain, cinematic lighting.
```

Midjourney: append `--ar 16:9 --style raw --cref <face-url> --cw 40`
(a low `--cw` keeps the face but lets the outfit change and drops the glasses).

## 5. Tips for a consistent face

- Generate the **still first**, pick the best face match, then use it as the
  start frame for image-to-video. Face drift is much lower than text-to-video.
- If the model keeps adding glasses, generate the still, then remove glasses
  with an inpainting pass before animating.
- Keep the shot 6–8 s; long clips with six moving creatures tend to break
  (animals merging, extra legs). If that happens, generate two passes
  (man + lion + knights, then wolf + tiger + eagle) and composite.
- Add an extra 5–10% of slow motion in an editor rather than prompting
  for very slow motion, which often freezes the animals.
