# sister-website
import streamlit as st

st.set_page_config(
    page_title="My Sister 👑",
    page_icon="👑",
    layout="centered"
)

# ---- PAGE STATE ----
if "page" not in st.session_state:
    st.session_state.page = "home"


def go(page_name):
    st.session_state.page = page_name
    st.rerun()


# ---- HOME PAGE ----
if st.session_state.page == "home":
    st.title("Official Website of My Sister 👑")
    st.write("Proceed only if you can handle the truth 😈")

    st.markdown("---")
    st.button(
        "Enter at your own risk →",
        on_click=go,
        args=("roast",),
        use_container_width=True
    )


# ---- ROAST PAGE ----
elif st.session_state.page == "roast":
    st.title("Let’s Be Honest 😌")

    st.markdown("""
    - Certified Drama Queen 👑  
    - Overreacts first, asks questions later  
    - Mood swings faster than Wi-Fi  
    - Still thinks she’s always right (she’s not)
    """)

    st.markdown("---")

    col1, col2 = st.columns(2)

    with col1:
        st.button("⬅ Back", on_click=go, args=("home",), use_container_width=True)

    with col2:
        st.button("Okay okay… jokes aside ❤️ →", on_click=go, args=("pause",), use_container_width=True)


# ---- PAUSE PAGE ----
elif st.session_state.page == "pause":
    st.title("Jokes aside…")
    st.write("This part actually matters.")

    st.markdown("---")

    col1, col2 = st.columns(2)

    with col1:
        st.button("⬅ Back", on_click=go, args=("roast",), use_container_width=True)

    with col2:
        st.button("Continue →", on_click=go, args=("love",), use_container_width=True)


# ---- LOVE PAGE ----
elif st.session_state.page == "love":
    st.title("All jokes aside…")

    st.markdown("""
    You’re dramatic.  
    You’re stubborn.  
    You’re impossible sometimes.  

    But you’re also strong, kind,  
    and one of the best humans I know.  

    I’m proud of you. Always. ❤️  
    """)

    st.markdown("— *Your favorite sibling 😌*")

    st.markdown("---")

    col1, col2 = st.columns(2)

    with col1:
        st.button("⬅ Back", on_click=go, args=("pause",), use_container_width=True)

    with col2:
        st.button("Celebrate 🎉", use_container_width=True)
        st.balloons()
