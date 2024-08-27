# 🎈 Blank app template

A simple Streamlit app template for you to modify!

[![Open in Streamlit](https://static.streamlit.io/badges/streamlit_badge_black_white.svg)](https://blank-app-template.streamlit.app/)

### How to run it on your own machine

1. Install the requirements

   ```
   $ pip install -r requirements.txt
   ```

2. Run the app

   ```
   $ streamlit run streamlit_app.py
   ```


pip install streamlit

import streamlit as st

def calculate_final_price(rate_pkrz, quantity, weight, slab_rate_pkr, usa_rate, percentage):
    rate_x_qty = rate_pkrz * quantity
    weight_x_slab = weight * slab_rate_pkr
    total_sum = rate_x_qty + weight_x_slab
    result_after_division = total_sum / usa_rate
    final_price = result_after_division + (percentage / 100) * result_after_division
    return final_price

st.title("Price Calculator")

rate_pkrz = st.number_input("Rate (PKRZ)", value=100)
quantity = st.number_input("Quantity", value=2000)
weight = st.number_input("Weight", value=50)
slab_rate_pkr = st.number_input("Slab Rate (PKR)", value=20)
usa_rate = st.number_input("USA Rate", value=270)
percentage = st.number_input("Percentage", value=10)

if st.button("Calculate"):
    final_price = calculate_final_price(rate_pkrz, quantity, weight, slab_rate_pkr, usa_rate, percentage)
    st.write(f"The final price is: {final_price:.2f} PKR")

