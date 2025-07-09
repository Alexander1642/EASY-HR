from playwright.sync_api import sync_playwright
import pickle

def save_cookies(context, path='cookies.pkl'):
    with open(path, 'wb') as f:
        pickle.dump(context.storage_state(), f)

def load_cookies(context, path='cookies.pkl'):
    with open(path, 'rb') as f:
        state = pickle.load(f)
        context.add_cookies(state['cookies'])

# 第一次扫码登录并保存 cookies
with sync_playwright() as p:
    browser = p.chromium.launch(headless=False)
    context = browser.new_context()
    page = context.new_page()
    page.goto("https://www.zhipin.com/web/user/")
    input("扫码登录后按Enter继续...")
    save_cookies(context)
    browser.close()
