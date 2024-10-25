<img width="1280" alt="readme-banner" src="https://github.com/user-attachments/assets/35332e92-44cb-425b-9dff-27bcf1023c6c">

# ⏰🗺️🧮🗓️ 4C's 🗓️🧮🗺️⏰


## Basic Details
### Team Name: Useless_Witches


### Team Members
- Team Lead: Aemilia Rose P J - Albertian Institute Of Science and Technology
- Member 2: Devika Thampi - Albertian Institute Of Science and Technology
- Member 3: Anjali Binu - Albertian Institute Of Science and Technology

### Project Description
Always Wrong Calculator : 
Launching a Calculator that is processed to get two numbers from the user to do four types of arithmetic operations . However , the twist comes during the execution of the code , when asked to do addition ,  the stupid calculator may do division or whichever arithmetic operator the computer prefers.…. Hence , the name Always Wrong Calculator .

Twister Calendar :
Presenting a Calendar that has more holidays than working days , favorable to all students and lazy bums . It is charismatic , has minimal working days , new names for each day of the week with lots of emojis .

Animistic World Map : 
Introducing a map that has a mind of its own . The user has the ability to show a country on the map which they prefer , nonetheless , the stubborn map only displays the country which the computer chooses .
 
The Capsized Clock : 
Exhibiting an emotional clock , it may always be wrong , it could be too emotional . Despite that , I bet this clock would make anyone's day. 

Summary : 
The user is given the ability to choose any of the given applications from above . Nevertheless , the pig-headed computer chooses the option preferable to them.

### The Problem (that doesn't exist)
In a world full of pessimism , our team introduces a set of applications to inject fun to the world.

### The Solution (that nobody asked for)
The applications present give a contrast of ourselves , instead of overthinking it does everything in the heat of the moment . 

## Technical Details
### Technologies/Components Used
For Software:
- Language Used : Python
- Libraries Used :
  1. Calender
  2. HTML
  3. Random
  4. DateTime
  5. Plotly.Express
 
For Hardware:
- Laptop
- Phone
- Tablet

### Project Documentation
For Software: # -*- coding: utf-8 -*-
"""USELESS_WITCHES.ipynb

Automatically generated by Colab.

Original file is located at
    https://colab.research.google.com/drive/1XGSAoiw0ZKm3U4Z4SX5e3_O6FkKi6JhP
"""

def Useless_Calculator():
  print('\n')
  print('Options available :\n1.Addition\n2.Subtraction\n3.Multiplication \n4.Division') #TO SHOW THE OPTIONS
  while True :
    num1=int(input('Enter the number1:'))
    num2=int(input('Enter the number2:'))
    ch= int(input('Enter your choice : '))
    if ch==1:
      sum1=num1/num2
    if num2!=0: #DENOMINATOR SHOULD NOT BE ZERO
      print('{num1} + {num2} =',sum1)
    elif ch==2:
      sum2=num1+num2
      print('{num1} - {num2} =',sum2)
    elif ch==3:
      sum3= num1-num2
      print('{num1} × {num2} =',sum3)
    elif ch==4:
      sum4=num1*num2
      print('{num1} ÷ {num2} =', sum4)
    else :  # FOR ANY NUMBER OTHER THAN 1- 4
      print('better  luck  next time fellas ')
      break

import calendar
from IPython.display import HTML, display
def create_useless_calendar():
    """Generates a quirky calendar for 2024 with weekday holidays, weekend workdays,
    aligned dates, and highlights a user-specified date."""
    year = 2024
    weekday_holidays = {
        0: "🌀Mind-Bending Monday🌀",
        1: "🌮Taco-Tasting Tuesday🌮",
        2: "🤪Wacky Wednesday🤪",
        3: "🚀Thrilling Thursday🚀",
        4: "🕺🕺Funky Friday🕺"  # Added extra dancing emoji
    }
    # Get user input for the date to highlight with validation
    while True:
        try:
            month_input = int(input("Enter the month (1-12): "))
            day_input = int(input("Enter the day (1-31): "))
            # Check if the date is valid using calendar module
            if 1 <= month_input <= 12 and 1 <= day_input <= calendar.monthrange(year, month_input)[1]:
                break  # Exit loop if date is valid
            else:
                print("Invalid date. Please enter a valid month and day for 2024.")
        except ValueError:
            print("Invalid input. Please enter numbers only.")
    cal = calendar.Calendar()
    calendar_output = ""
    for month in range(1, 13):
        calendar_output += f"<br><h3>{calendar.month_name[month]} {year}</h3><br>"
        calendar_output += "<table style='width:100%; border-collapse: collapse;'>"
        calendar_output += "<tr>"
        for day_index in range(7):
            calendar_output += f"<th style='border: 1px solid black; padding: 5px;'>{calendar.day_abbr[day_index]}</th>"
        calendar_output += "</tr>"
        for week in cal.monthdayscalendar(year, month):
            calendar_output += "<tr>"
            for day, weekday in enumerate(week):
                if weekday != 0:
                    date_str = f"{month}/{weekday}/{year}"
                    highlight = (month == month_input and weekday == day_input)

                    cell_content = f"{weekday:2} - {date_str:>10}"
                    if highlight:
                        cell_content = f"<b><mark>{cell_content}</mark></b>"
                    elif day in weekday_holidays and day != 5 and day != 6:
                        cell_content = f"{weekday:2} - {weekday_holidays[day]:<25} (Holiday) - {date_str:>10}"
                    elif day == 5:
                        cell_content = f"{weekday:2} - Super Saturday (Work) 🤮 - {date_str:>10}"  # Added vomit emoji
                    elif day == 6:
                        cell_content = f"{weekday:2} - Scrum Sunday (Work) 🤮 - {date_str:>10}"  # Added vomit emoji
                    calendar_output += f"<td style='border: 1px solid black; padding: 5px; text-align: center;'>{cell_content}</td>"
                else:
                    calendar_output += "<td style='border: 1px solid black; padding: 5px;'></td>"
            calendar_output += "</tr>"
        calendar_output += "</table><br>"
    display(HTML(calendar_output))


def Useless_Map():
    import random
    import plotly.express as px
    country_fake = input("enter a country name : ") # Country name to be discplayed , but not take into consideration
    randomly_generated_number = random.randint(1,195) # Number generated randomly, which desides the contry to be highlighted in the map
    # 195 countries with their assigned numbers
    if randomly_generated_number == 1:
        country = 'India'
    elif randomly_generated_number == 2:
        country = 'China'
    elif randomly_generated_number == 3:
        country = 'United States'
    elif randomly_generated_number == 4:
        country = 'Indonesia'
    elif randomly_generated_number == 5:
        country = 'Pakistan'
    elif randomly_generated_number == 6:
        country = 'Nigeria'
    elif randomly_generated_number == 7:
        country = 'Brazil'
    elif randomly_generated_number == 8:
        country = 'Bangladesh'
    elif randomly_generated_number == 9:
        country = 'Russia'
    elif randomly_generated_number == 10:
        country = 'Ethiopia'
    elif randomly_generated_number == 11:
        country = 'Mexico'
    elif randomly_generated_number == 12:
        country = 'Japan'
    elif randomly_generated_number == 13:
        country = 'Egypt'
    elif randomly_generated_number == 14:
        country = 'Philippines'
    elif randomly_generated_number == 15:
        country = 'DR Congo'
    elif randomly_generated_number == 16:
        country = 'Vietnam'
    elif randomly_generated_number == 17:
        country = 'Iran'
    elif randomly_generated_number == 18:
        country = 'Turkey'
    elif randomly_generated_number == 19:
        country = 'Germany'
    elif randomly_generated_number == 20:
        country = 'Thailand'
    elif randomly_generated_number == 21:
        country = 'United Kingdom'
    elif randomly_generated_number == 22:
        country = 'Tanzania'
    elif randomly_generated_number == 23:
        country = 'France'
    elif randomly_generated_number == 24:
        country = 'South Africa'
    elif randomly_generated_number == 25:
        country = 'Italy'
    elif randomly_generated_number == 26:
        country = 'Kenya'
    elif randomly_generated_number == 27:
        country = 'Myanmar'
    elif randomly_generated_number == 28:
        country = 'Colombia'
    elif randomly_generated_number == 29:
        country = 'South Korea'
    elif randomly_generated_number == 30:
        country = 'Sudan'
    elif randomly_generated_number == 31:
        country = 'Uganda'
    elif randomly_generated_number == 32:
        country = 'Spain'
    elif randomly_generated_number == 33:
        country = 'Algeria'
    elif randomly_generated_number == 34:
        country = 'Iraq'
    elif randomly_generated_number == 35:
        country = 'Argentina'
    elif randomly_generated_number == 36:
        country = 'Afghanistan'
    elif randomly_generated_number == 37:
        country = 'Yemen'
    elif randomly_generated_number == 38:
        country = 'Canada'
    elif randomly_generated_number == 39:
        country = 'Poland'
    elif randomly_generated_number == 40:
        country = 'Morocco'
    elif randomly_generated_number == 41:
        country = 'Angola'
    elif randomly_generated_number == 42:
        country = 'Ukraine'
    elif randomly_generated_number == 43:
        country = 'Uzbekistan'
    elif randomly_generated_number == 44:
        country = 'Malaysia'
    elif randomly_generated_number == 45:
        country = 'Mozambique'
    elif randomly_generated_number == 46:
        country = 'Ghana'
    elif randomly_generated_number == 47:
        country = 'Peru'
    elif randomly_generated_number == 48:
        country = 'Saudi Arabia'
    elif randomly_generated_number == 49:
        country = 'Madagascar'
    elif randomly_generated_number == 50:
        country = "Côte d'Ivoire"
    elif randomly_generated_number == 51:
        country = 'Nepal'
    elif randomly_generated_number == 52:
        country = 'Cameroon'
    elif randomly_generated_number == 53:
        country = 'Venezuela'
    elif randomly_generated_number == 54:
        country = 'Niger'
    elif randomly_generated_number == 55:
        country = 'Australia'
    elif randomly_generated_number == 56:
        country = 'North Korea'
    elif randomly_generated_number == 57:
        country = 'Syria'
    elif randomly_generated_number == 58:
        country = 'Mali'
    elif randomly_generated_number == 59:
        country = 'Burkina Faso'
    elif randomly_generated_number == 60:
        country = 'Sri Lanka'
    elif randomly_generated_number == 61:
        country = 'Malawi'
    elif randomly_generated_number == 62:
        country = 'Zambia'
    elif randomly_generated_number == 63:
        country = 'Kazakhstan'
    elif randomly_generated_number == 64:
        country = 'Chad'
    elif randomly_generated_number == 65:
        country = 'Chile'
    elif randomly_generated_number == 66:
        country = 'Romania'
    elif randomly_generated_number == 67:
        country = 'Somalia'
    elif randomly_generated_number == 68:
        country = 'Senegal'
    elif randomly_generated_number == 69:
        country = 'Guatemala'
    elif randomly_generated_number == 70:
        country = 'Netherlands'
    elif randomly_generated_number == 71:
        country = 'Ecuador'
    elif randomly_generated_number == 72:
        country = 'Cambodia'
    elif randomly_generated_number == 73:
        country = 'Zimbabwe'
    elif randomly_generated_number == 74:
        country = 'Guinea'
    elif randomly_generated_number == 75:
        country = 'Benin'
    elif randomly_generated_number == 76:
        country = 'Rwanda'
    elif randomly_generated_number == 77:
        country = 'Burundi'
    elif randomly_generated_number == 78:
        country = 'Bolivia'
    elif randomly_generated_number == 79:
        country = 'Tunisia'
    elif randomly_generated_number == 80:
        country = 'South Sudan'
    elif randomly_generated_number == 81:
        country = 'Haiti'
    elif randomly_generated_number == 82:
        country = 'Belgium'
    elif randomly_generated_number == 83:
        country = 'Jordan'
    elif randomly_generated_number == 84:
        country = 'Dominican Republic'
    elif randomly_generated_number == 85:
        country = 'United Arab Emirates'
    elif randomly_generated_number == 86:
        country = 'Cuba'
    elif randomly_generated_number == 87:
        country = 'Honduras'
    elif randomly_generated_number == 88:
        country = 'Czech Republic'
    elif randomly_generated_number == 89:
        country = 'Sweden'
    elif randomly_generated_number == 90:
        country = 'Tajikistan'
    elif randomly_generated_number == 91:
        country = 'Papua New Guinea'
    elif randomly_generated_number == 92:
        country = 'Portugal'
    elif randomly_generated_number == 93:
        country = 'Azerbaijan'
    elif randomly_generated_number == 94:
        country = 'Greece'
    elif randomly_generated_number == 95:
        country = 'Hungary'
    elif randomly_generated_number == 96:
        country = 'Togo'
    elif randomly_generated_number == 97:
        country = 'Israel'
    elif randomly_generated_number == 98:
        country = 'Austria'
    elif randomly_generated_number == 99:
        country = 'Belarus'
    elif randomly_generated_number == 100:
        country = 'Switzerland'
    elif randomly_generated_number == 101:
        country = 'Sierra Leone'
    elif randomly_generated_number == 102:
        country = 'Laos'
    elif randomly_generated_number == 103:
        country = 'Turkmenistan'
    elif randomly_generated_number == 104:
        country = 'Libya'
    elif randomly_generated_number == 105:
        country = 'Kyrgyzstan'
    elif randomly_generated_number == 106:
        country = 'Paraguay'
    elif randomly_generated_number == 107:
        country = 'Nicaragua'
    elif randomly_generated_number == 108:
        country = 'Bulgaria'
    elif randomly_generated_number == 109:
        country = 'Serbia'
    elif randomly_generated_number == 110:
        country = 'El Salvador'
    elif randomly_generated_number == 111:
        country = 'Congo'
    elif randomly_generated_number == 112:
        country = 'Denmark'
    elif randomly_generated_number == 113:
        country = 'Singapore'
    elif randomly_generated_number == 114:
        country = 'Lebanon'
    elif randomly_generated_number == 115:
        country = 'Finland'
    elif randomly_generated_number == 116:
        country = 'Liberia'
    elif randomly_generated_number == 117:
        country = 'Norway'
    elif randomly_generated_number == 118:
        country = 'Slovakia'
    elif randomly_generated_number == 119:
        country = 'State of Palestine'
    elif randomly_generated_number == 120:
        country = 'Central African Republic'
    elif randomly_generated_number == 121:
        country = 'Oman'
    elif randomly_generated_number == 122:
        country = 'Ireland'
    elif randomly_generated_number == 123:
        country = 'New Zealand'
    elif randomly_generated_number == 124:
        country = 'Mauritania'
    elif randomly_generated_number == 125:
        country = 'Costa Rica'
    elif randomly_generated_number == 126:
        country = 'Kuwait'
    elif randomly_generated_number == 127:
        country = 'Panama'
    elif randomly_generated_number == 128:
        country = 'Croatia'
    elif randomly_generated_number == 129:
        country = 'Georgia'
    elif randomly_generated_number == 130:
        country = 'Eritrea'
    elif randomly_generated_number == 131:
        country = 'Mongolia'
    elif randomly_generated_number == 132:
        country = 'Uruguay'
    elif randomly_generated_number == 133:
        country = 'Bosnia and Herzegovina'
    elif randomly_generated_number == 134:
        country = 'Qatar'
    elif randomly_generated_number == 135:
        country = 'Moldova'
    elif randomly_generated_number == 136:
        country = 'Namibia'
    elif randomly_generated_number == 137:
        country = 'Armenia'
    elif randomly_generated_number == 138:
        country = 'Lithuania'
    elif randomly_generated_number == 139:
        country = 'Jamaica'
    elif randomly_generated_number == 140:
        country = 'Albania'
    elif randomly_generated_number == 141:
        country = 'Gambia'
    elif randomly_generated_number == 142:
        country = 'Gabon'
    elif randomly_generated_number == 143:
        country = 'Botswana'
    elif randomly_generated_number == 144:
        country = 'Lesotho'
    elif randomly_generated_number == 145:
        country = 'Guinea-Bissau'
    elif randomly_generated_number == 146:
        country = 'Slovenia'
    elif randomly_generated_number == 147:
        country = 'Equatorial Guinea'
    elif randomly_generated_number == 148:
        country = 'Latvia'
    elif randomly_generated_number == 149:
        country = 'North Macedonia'
    elif randomly_generated_number == 150:
        country = 'Bahrain'
    elif randomly_generated_number == 151:
        country = 'Trinidad and Tobago'
    elif randomly_generated_number == 152:
        country = 'Timor-Leste'
    elif randomly_generated_number == 153:
        country = 'Estonia'
    elif randomly_generated_number == 154:
        country = 'Cyprus'
    elif randomly_generated_number == 155:
        country = 'Mauritius'
    elif randomly_generated_number == 156:
        country = 'Eswatini'
    elif randomly_generated_number == 157:
        country = 'Djibouti'
    elif randomly_generated_number == 158:
        country = 'Fiji'
    elif randomly_generated_number == 159:
        country = 'Comoros'
    elif randomly_generated_number == 160:
        country = 'Guyana'
    elif randomly_generated_number == 161:
        country = 'Solomon Islands'
    elif randomly_generated_number == 162:
        country = 'Bhutan'
    elif randomly_generated_number == 163:
        country = 'Luxembourg'
    elif randomly_generated_number == 164:
        country = 'Montenegro'
    elif randomly_generated_number == 165:
        country = 'Suriname'
    elif randomly_generated_number == 166:
        country = 'Malta'
    elif randomly_generated_number == 167:
        country = 'Maldives'
    elif randomly_generated_number == 168:
        country = 'Micronesia'
    elif randomly_generated_number == 169:
        country = 'Cabo Verde'
    elif randomly_generated_number == 170:
        country = 'Brunei'
    elif randomly_generated_number == 171:
        country = 'Belize'
    elif randomly_generated_number == 172:
        country = 'Bahamas'
    elif randomly_generated_number == 173:
        country = 'Iceland'
    elif randomly_generated_number == 174:
        country = 'Vanuatu'
    elif randomly_generated_number == 175:
        country = 'Barbados'
    elif randomly_generated_number == 176:
        country = 'Sao Tome & Principe'
    elif randomly_generated_number == 177:
        country = 'Samoa'
    elif randomly_generated_number == 178:
        country = 'Saint Lucia'
    elif randomly_generated_number == 179:
        country = 'Kiribati'
    elif randomly_generated_number == 180:
        country = 'Seychelles'
    elif randomly_generated_number == 181:
        country = 'Grenada'
    elif randomly_generated_number == 182:
        country = 'Tonga'
    elif randomly_generated_number == 183:
        country = 'St. Vincent & Grenadines'
    elif randomly_generated_number == 184:
        country = 'Antigua and Barbuda'
    elif randomly_generated_number == 185:
        country = 'Andorra'
    elif randomly_generated_number == 186:
        country = 'Dominica'
    elif randomly_generated_number == 187:
        country = 'Saint Kitts & Nevis'
    elif randomly_generated_number == 188:
        country = 'Liechtenstein'
    elif randomly_generated_number == 189:
        country = 'Monaco'
    elif randomly_generated_number == 190:
        country = 'Marshall Islands'
    elif randomly_generated_number == 191:
        country = 'San Marino'
    elif randomly_generated_number == 192:
        country = 'Palau'
    elif randomly_generated_number == 193:
        country = 'Nauru'
    elif randomly_generated_number == 194:
        country = 'Tuvalu'
    elif randomly_generated_number == 195:
        country = 'Holy See'
    value = input("enter color to be higlighted : ")
    data = {'country':[country],'value':[value]}
    fig = px.choropleth(data,
                    locations='country',
                    locationmode='country names',
                    color='value',
                    color_continuous_scale="inferno",
                    title=f'Country higlighted in map : {country}') # Code for displaying the map
    fig.show()

def weather_program():
  from IPython import get_ipython
  from IPython.display import display
  def get_wrong_weather_kerala_with_emoji(district):
    import random
    districts = ["Ernakulam", "Thiruvananthapuram", "Kozhikode", "Thrissur", "Kollam", "Kottayam", "Palakkad", "Malappuram", "Alappuzha", "Kannur", "Kasaragod", "Pathanamthitta", "Idukki", "Wayanad"]
    weather_conditions = ["sunny", "rainy", "cloudy", "windy", "stormy"]
    emojis = {"sunny": "☀️", "rainy": "🌧️", "cloudy": "☁️", "windy": "💨", "stormy": "⛈️"}
    temperature = random.randint(-10, 50)
    # Ensure wrong output:
    random_district = random.choice(districts)
    while random_district == district:
      random_district = random.choice(districts)
    condition_index = random.randint(0, len(weather_conditions) - 1)
    # Intentionally use a wrong emoji:
    emoji_index = (condition_index + random.randint(1, len(emojis) - 1)) % len(emojis)
    emoji = list(emojis.values())[emoji_index]
    weather_description = f"The weather in {random_district} is {weather_conditions[condition_index]} {emoji} with a temperature of {temperature}°C."
    return weather_description
    # Call the function to get the weather information:
    district = input("Enter your preferred district in Kerala: ")
    weather_info = get_wrong_weather_kerala_with_emoji(district)
    print(weather_info)

def tell_wrong_time_with_emoji():
  """Tells the wrong time with a random emoji."""
  import datetime
  import random
  def get_wrong_time():
    """Generates a random time offset from the current time."""
    now = datetime.datetime.now()
    offset_hours = random.randint(-12, 12)
    offset_minutes = random.randint(-59, 59)
    offset_seconds = random.randint(-59, 59)
    wrong_time = now + datetime.timedelta(hours=offset_hours, minutes=offset_minutes, seconds=offset_seconds)
    return wrong_time.strftime("%I:%M:%S %p")
  def get_random_emoji():
    """Returns a random emoji from a list."""
    emojis = ["😂", "🤣", "😊", "😎", "🤔", "🥳", "🥺", "🥰", "🤯", "🤩", "🤬"]
    return random.choice(emojis)
  while True:
    user_input = input("Do you want to know the time? (yes/no): ")
    if user_input.lower() == "yes":
      wrong_time = get_wrong_time()
      emoji = get_random_emoji()
      print(f"The time is: {wrong_time} {emoji}")
    elif user_input.lower() == "no":
      print("Why no? 🥺")  # Print with sad emoji
      break
    else:
      print("Invalid input. Please enter 'yes' or 'no'.")

while True :
  import random
  choose = int(input("Optionas Available :\n1.Always Wrong Calculator\n2.Twister Calendar\n3.Animistic World Map\n4.The Capsized Clock\nChoose your favorite option : "))
  option = random.randint(1,4)
  if option == 1:
    Useless_Calculator()
  elif option == 2 :
    create_useless_calendar()
  elif option == 3 :
     Useless_Map()
  elif option == 4 :
    tell_wrong_time_with_emoji()
    break

# Screenshots (Add at least 3)
![Screenshot1](Add screenshot 1 here with proper name)
*Add caption explaining what this shows*

![Screenshot2](Add screenshot 2 here with proper name)
*Add caption explaining what this shows*

![Screenshot3](Add screenshot 3 here with proper name)
*Add caption explaining what this shows*

# Diagrams
![Workflow](Add your workflow/architecture diagram here)
*Add caption explaining your workflow*

For Hardware:

# Schematic & Circuit
![Circuit](Add your circuit diagram here)
*Add caption explaining connections*

![Schematic](Add your schematic diagram here)
*Add caption explaining the schematic*

### Project Demo
# Video
https://drive.google.com/file/d/1et-nhOGm56UF4YS_vB3EBE-6HIQgidnL/view?usp=drive_link
This video shows two outputs out of five available.

# Additional Demos
1. https://drive.google.com/file/d/1SuStp2hSEzt0qJCccgymv-668iWe1pEm/view?usp=drive_link
2. https://drive.google.com/file/d/1lm74hJpSFbTc08-ho2RABXYig8wi342C/view?usp=drive_link

## Team Contributions
- Aemilia Rose P J: Helped in making Calendar and Clock
- Devika Thampi: Helped in making Calculator and in debugging
- Anjali Binu: Helped in making Map and overall code

---
Made with ❤️ at TinkerHub Useless Projects 

![Static Badge](https://img.shields.io/badge/TinkerHub-24?color=%23000000&link=https%3A%2F%2Fwww.tinkerhub.org%2F)
![Static Badge](https://img.shields.io/badge/UselessProject--24-24?link=https%3A%2F%2Fwww.tinkerhub.org%2Fevents%2FQ2Q1TQKX6Q%2FUseless%2520Projects)



