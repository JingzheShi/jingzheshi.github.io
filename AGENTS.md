# Homepage project memory

- This directory is a clone of `https://github.com/JingzheShi/jingzheshi.github.io`, the source for `https://jingzheshi.github.io/`.
- GitHub Pages uses the `master` branch root with the legacy Pages build. There is no build step; `index.html` is English, `index_cn.html` is Chinese, and `stylesheet.css` holds shared styles.
- Keep publication entries in newest-first order in both HTML files. Each entry uses a two-cell table row. A paper without a published figure can use a text label in the left cell; do not reuse an unrelated paper image.
- Pushing changes to `index_cn.html` on `master` triggers `.github/workflows/sync-chinese.yml`, which publishes the Chinese mirror at `https://jingzhe-cn.github.io/`.
- The 2026-09-30 paper update is source commit `5b6119e6cc9c5cdc37d6497f2bd7678c9af5bf54`. The title, authors, and abstract are on `https://arxiv.org/abs/2609.32665`; Qinwei Ma's homepage states “Preprint, under review at ICLR 2027” and marks Qinwei Ma and Jingzhe Shi as equal contributors.
- After a push, GitHub Pages can briefly serve the previous HTML while its build is running. Check `gh api repos/JingzheShi/jingzheshi.github.io/pages/builds/latest`, then fetch both live HTML URLs and verify the first publication title and arXiv link.
