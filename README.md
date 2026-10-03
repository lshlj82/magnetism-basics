# Moving Charges and Magnetic Fields

An interactive, browser-based demo of the basic concepts of magnetism. It covers the force a magnetic field exerts on moving charges and currents, and the fields that currents create. It comes as two separate pages, one in English and one in Korean.

Created by **Claude Opus 5.5**, based on the lecture notes by **Sang Hoon Lee (이상훈)**.

> **한국어 요약:** 자기장이 움직이는 전하와 전류에 작용하는 힘, 그리고 전류가 만드는 자기장 등 자기의 기본 개념을 직접 조작해 볼 수 있는 인터랙티브 웹 데모입니다. 이상훈(Sang Hoon Lee)의 강의 노트를 바탕으로 Claude Opus 5.5가 만들었습니다. 한국어 페이지는 `magnetism-ko.html`입니다.

## Files

| File | Description |
| --- | --- |
| `magnetism-en.html` | American English version |
| `magnetism-ko.html` | Korean version (한국어) |
| `README.md` | This file |

Each page is a single self-contained HTML file with inline CSS and JavaScript. There is no build step and there are no dependencies. The only external request is to Google Fonts for IBM Plex Sans KR; if that request fails, the page falls back to system fonts. Each page links to the other language from its top bar.

## Running it

Open either file directly in a modern browser, or serve the folder locally:

```bash
python3 -m http.server 8000
# then visit http://localhost:8000/magnetism-en.html
```

### Publishing on GitHub Pages

1. Push these files to a repository.
2. In **Settings → Pages**, choose **Deploy from a branch**, then select your branch and the root folder.
3. Visit `https://<user>.github.io/<repo>/magnetism-en.html` or `.../magnetism-ko.html`.

These pages can share a repository with the companion demos on DC circuits (`circuits-*.html`) and RC circuits (`rc-*.html`). The file names don't collide.

## What's inside

The ten sections follow the order of the lecture notes. Every value is recomputed live as you move the controls.

1. **Magnetic force on a moving charge:** Set the angle φ between **v** and **B** and the sign of the charge. The page shows the force **F**<sub>B</sub> = q**v** × **B**, which points out of the page (⊙) or into it (⊗), and its magnitude in newtons. It also explains how the right-hand rule and the sign of q combine. A side note covers the units: T = N/(A·m) and 1 T = 10⁴ G.
2. **Crossed fields:** A particle flies between plates with **E** pointing down and **B** pointing into the page. Live arrows show the electric and magnetic forces acting on it. Press "Set v = E/B" and the particle goes straight, whatever the sign of its charge.
3. **Hall effect:** Carriers drift through a strip and are pushed to one side. Charge builds up there until the Hall field balances the magnetic force. You can switch between electrons and hypothetical positive carriers to see which side ends up at the higher potential. The Hall voltage V = Bi/(nle) is calculated for copper and for an example semiconductor.
4. **Circular motion:** Two particles move at different speeds in the same field. They trace circles of different radii but complete each lap at the same moment, because T = 2πm/(|q|B) does not depend on speed. The page gives real r, T, f, and ω for a proton, an electron, and an alpha particle. A side view shows the helical path, with its radius and pitch, when **v** is tilted relative to **B**.
5. **Force on a current-carrying wire:** A wire held between two clamps bows in the field, with F = iLB. The current can be pictured either as positive charges or as electrons, and both give the same force.
6. **Torque on a current loop:** A loop, seen edge-on, swings and settles in the field under the torque τ = NiAB sin θ. In motor mode the current flips every half turn, so the loop keeps spinning. A τ(θ) graph accompanies the loop.
7. **Biot–Savart law:** This section covers three geometries: a long straight wire (B = μ₀i/2πR, plus the case of a wire that is infinite on one side only), a circular arc (B = μ₀iφ/4πR, which becomes μ₀i/2R for a full circle), and a point on the axis of a loop. In each case the formula is checked against a numerical sum over 2000 current elements.
8. **Parallel currents:** Two wires attract each other when their currents point the same way and repel when they point opposite ways, with F/L = μ₀i<sub>a</sub>i<sub>b</sub>/2πd.
9. **Ampère's law:** You can drag a circular Ampère loop among three currents. The page computes ∮**B**·d**s** numerically and shows that it equals μ₀i<sub>enc</sub>, with each segment of the loop colored by the sign of **B**·d**s**. A graph shows the field inside and outside a thick wire.
10. **Solenoid:** A cross-section of a solenoid with a rectangular Ampère loop drawn on it, showing that B = μ₀in.

## Notes on the model

- The crossed-fields section uses arbitrary units so the motion is visible. Its only purpose is to show that the particle passes straight through when v = E/B. Every other section uses SI units.
- The semiconductor carrier density, n = 10²³ m⁻³, is an illustrative value.
- In the Hall-effect section, the way charge builds up over time is a qualitative animation. The Hall voltage it reports is the steady-state value.
- The solenoid section assumes an ideal solenoid, with a uniform field inside and zero field outside.
- The pages follow the system's light or dark setting. The decorative orbit in the header stays still under `prefers-reduced-motion`.

## Credits

- Lecture notes: Sang Hoon Lee (이상훈)
- Demo design and code: Claude Opus 5.5

## License

No license has been chosen yet. Before publishing, add a `LICENSE` file if you want others to be able to reuse the code, and confirm with the author of the lecture notes how their material may be shared.
