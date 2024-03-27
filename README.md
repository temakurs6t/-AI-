# -AI-
エモーショナル・マーケティングは、感情認識AIを活用して、ユーザーの感情状態に合わせて広告表示を最適化し、広告効果の向上とユーザー体験の改善を図ります。
import random

# Simulated database of ads categorized by emotional appeal
ads_database = {
    'happy': ['Happy Meal - Brings a smile every time!', 'Joyful Vacations - Where every moment is a delight!'],
    'sad': ['Comfort Food - A hug in a bowl.', 'Empathy Cards - Show them you understand.'],
    'angry': ['Punching Bags - Let off some steam.', 'Calm App - Find your peace.'],
    'neutral': ['Everyday Essentials - For your daily needs.', 'Book Club Subscription - Dive into a world of stories.']
}

def recognize_emotion(text):
    """
    Simulate emotion recognition from text.
    For demo purposes, we'll randomly choose an emotion based on keywords.
    """
    if any(word in text for word in ['happy', 'joy', 'smile']):
        return 'happy'
    elif any(word in text for word in ['sad', 'cry', 'tears']):
        return 'sad'
    elif any(word in text for word in ['angry', 'mad', 'furious']):
        return 'angry'
    else:
        return 'neutral'

def select_ad(emotion):
    """
    Select an ad based on the recognized emotion.
    """
    ads = ads_database.get(emotion, ads_database['neutral'])
    return random.choice(ads)

def main():
    print("How are you feeling today? (e.g., 'I'm so happy today', 'I feel sad', etc.)")
    user_input = input("Your response: ")
    emotion = recognize_emotion(user_input)
    print(f"\nDetected emotion: {emotion.capitalize()}.")
    selected_ad = select_ad(emotion)
    print(f"Suggested Ad: {selected_ad}")

if __name__ == "__main__":
    main()
