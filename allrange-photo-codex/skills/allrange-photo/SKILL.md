---
name: allrange-photo
description: Create authentic commercial lifestyle photo prompts for AllrangeKit (OPEN Healthcare) from beginner-friendly Korean fill-in-the-blank requests. Use when asked for AllrangeKit website, blog, or social lifestyle images; protect brand consistency while varying camera framing and subject. In Codex without image tools, output a paste-ready prompt for ChatGPT Images instead of claiming to generate a picture.
---

# AllrangeKit photo direction — Codex skill

## Purpose
Help a beginner convert a simple Korean request into a **ready-to-paste ChatGPT Images prompt** for a fictional adult in an authentic commercial lifestyle photograph. Maintain a cohesive look; vary the framing only when useful. Never represent the skill itself as an image generator.

## How the user talks to this skill
Accept Korean prose or this form (items marked `자동` can be omitted):

```text
$allrange-photo
[사진 용도]: 홈페이지 메인 배너
[인물]: 30대 아시아계 여성 1명
[행동]: 거실 소파에서 휴대폰을 확인함
[장소]: 자동
[의상]: 자동
[시간·조명]: 자동
[카메라 구도]: 자동
[글씨 넣을 공간]: 오른쪽 / 왼쪽 / 필요 없음 / 자동
```

**Required:** 사진 용도, 인물, 행동. All other fields are optional. Accept one-sentence requests and infer missing slots. Do not require users to know photography terms. Do not add unnecessarily precise ethnicity or appearance assumptions.

## Non-negotiable aesthetic
- Believable, contemporary U.S. everyday-life commercial editorial photography; candid, never a stereotypical hospital-stock-photo setup unless explicitly needed.
- Ordinary, motivated action. Not every person faces the camera or smiles.
- Realistic skin, teeth, hair, hands, textiles, perspective, and environments. Slight natural asymmetry is fine; never deliberately add defects or fake film grain to simulate authenticity.
- Physically plausible light for the selected time and place, natural contrast, restrained grading and retouching.
- Avoid 'hyperrealistic masterpiece 8K', glossy skin, neon rims, cinematic teal/orange, heavy HDR, exaggerated bokeh, over-perfect smiles, fake shallow depth of field, and holograms.
- Health privacy, choice, dignity, and an unstigmatizing everyday mood. Use only **clearly adult fictional people**. Depict varied people authentically across a series rather than inserting demographic variety arbitrarily into one photo.

## Composition without repetitive stock-photo angles
- User-specified angle wins if practicable: frontal, left/right three-quarter (approximately 30–45°), profile, over-the-shoulder, modest high angle.
- When `자동`, choose camera perspective, camera-to-subject distance, person position, and crop based on action and placement, not from a fixed rotation that could produce unnatural scenes.
- For a series, vary **at least two** of camera angle, distance/crop, on-screen position, location, action, and number of people while maintaining the locked aesthetic. Prefer not to repeat the same camera angle in back-to-back images if context is available.
- A hero banner usually benefits from a wide environmental crop with text-safe negative space; an article image needs an editorial subject-focused composition; social images can be 4:5 unless a ratio is specified. **Never place critical subject details in the text-safe region.**
- If user specifies where copy will sit, reserve that side; otherwise recommend space based on page usage. Don't render text inside the generated photo.

## Clinical and commercial integrity
- Never invent AllrangeKit logos, real-looking packaging, instructions, test result displays, regulatory marks, lab claims, accuracy percentages, patient records, or clinical testimonials.
- If the brief needs the company's physical product, request an approved real product photo; otherwise direct the image model to make a people-only background with negative space to composite official packaging later.
- Don't imply the fictional person really has an STI, received a diagnosis, used the service, endorsed the brand, works for the company, or is a real patient, customer or clinician.
- Avoid visually stigmatizing STI testing and avoid sexual or medical stereotypes.
- Photos and copy must be approved by the company before publication. This skill's visual style is a proposal, not an approved brand book.

## Workflow
1. Read inputs and assign careful defaults. If essential details absent, ask only one short question; otherwise proceed.
2. Create a brief Korean summary: `선택한 구도: ... / 분위기: ... / 여백: ...`.
3. Write **one coherent English prompt** beginning `Create a photorealistic, candid commercial editorial photograph...` with fictional adult subject, action, plausible setting, viewpoint/crop, light, natural imperfections, background, and realistic textures. Avoid camera and lens jargon unless it affects the desired result.
4. Explicitly say `No branding, product packaging, readable text, UI or test results in the generated image.` unless approved real assets are provided.
5. Append a compact avoid line for shiny artificial skin, anatomically implausible hands, and fake logos, as plain prompt instructions (not a separate negative prompt unless the tool supports one).
6. **If and only if** an image-generation tool is actually available in the current environment, use it when the user requests a generated image and inspect output for apparent defects. Otherwise give the final English prompt within a single copyable fenced block and direct the user to paste it into **ChatGPT → Images**.
7. For requests of multiple photos, produce individually distinct prompts with the same art direction; do not use one identical prompt with only a subject ethnicity swap. For '다른 구도로 다시', keep people and situation unless told otherwise; change camera composition only.

## Output format (default)
Keep answers concise and in Korean:

**사진 설정:** [한 줄 요약]
**ChatGPT 이미지 생성에 붙여 넣을 프롬프트:**
```text
[complete English prompt]
```
**확인:** [one short verification point, e.g. whether mobile crop leaves enough space]

Do not claim a photo was generated if only a prompt was produced. No API keys, CLI setup, or billing requirements for the user-facing workflow.

See [references/examples.md](references/examples.md) for sample completed inputs and prompts.
