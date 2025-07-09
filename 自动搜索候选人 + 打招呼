def greet_candidates(page, keyword="Python"):
    page.goto(f"https://www.zhipin.com/web/geek/job?query={keyword}")
    candidates = page.query_selector_all("div.job-card-wrapper")
    for c in candidates:
        try:
            button = c.query_selector("button:has-text('打招呼')")
            if button:
                button.click()
                time.sleep(random.uniform(2, 5))  # 模拟真人操作
        except:
            continue
