const topButton = document.querySelector(".top-button");

window.addEventListener("scroll", () => {
  topButton.classList.toggle("is-visible", window.scrollY > 500);
});

topButton.addEventListener("click", () => {
  window.scrollTo({ top: 0, behavior: "smooth" });
});

const viewCount = document.querySelector("#view-count");

async function updateViews() {
  if (!viewCount) return;

  try {
    const response = await fetch("https://api.counterapi.dev/v1/hardikgargok-github-io/page-views/up", {
      cache: "no-store"
    });

    if (!response.ok) throw new Error("View counter failed");

    const data = await response.json();
    viewCount.textContent = Number(data.count || 0).toLocaleString("en-US");
  } catch {
    viewCount.textContent = "--";
  }
}

updateViews();
