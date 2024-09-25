import streamlit as st


# Wall Coefficient function
def wall_coefficient(Fs, Ts, Es, R, C, P):
    W = (Fs * (Ts + Es)) / (R + (C * P) ** 0.5)
    return W


# Streamlit app UI
def main():
    # Set page title and layout
    st.set_page_config(page_title="Wall Coefficient Calculator", layout="centered")

    # Header
    st.title("🚀 Wall Coefficient Calculator")
    st.markdown(
        """
        **Is the wall you're hitting a sign of failure or the launchpad to success?**
        Use this tool to find out whether you're facing a temporary setback or about to break through!
        """
    )

    # Input sliders and text inputs
    st.header("🔧 Input Your Values")

    current_effort = st.slider("Current Effort and Focus (Fs)", 0, 100, 80)
    time_invested = st.slider("Time Invested (Ts) in months", 0, 36, 12)
    emotional_resilience = st.slider("Emotional Resilience (Es)", 0, 100, 70)
    resistance = st.slider("Resistance (R)", 0, 100, 60)
    complexity = st.slider("Complexity of Problem (C)", 0, 100, 50)
    perceived_success_prob = st.slider("Perceived Probability of Success (P)", 0.0, 1.0, 0.6, step=0.01)

    # Button to calculate
    if st.button("Calculate Wall Coefficient"):
        # Calculate Wall Coefficient
        W = wall_coefficient(current_effort, time_invested, emotional_resilience, resistance, complexity,
                             perceived_success_prob)

        # Display results with dynamic interpretation
        st.subheader("📊 Results")
        st.write(f"**Your Wall Coefficient is: {W:.2f}**")

        if W > 1:
            st.success("You're on the verge of a breakthrough! Keep pushing, and success is just around the corner.")
        elif 0.5 < W <= 1:
            st.warning(
                "You're close, but there's more work to do. Stay focused, make some adjustments, and you’ll get there.")
        else:
            st.error(
                "It might be time to reassess your approach. The wall you're facing could be signaling the need for a pivot.")

    # Footer
    st.markdown(
        """
        ---
        **Wall Coefficient Calculator** | Created by a world-class mathematician and data scientist
        """
    )


# Run the app
if __name__ == "__main__":
    main()
