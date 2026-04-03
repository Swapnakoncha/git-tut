# 💰 Interest Calculator

A simple JavaScript-based web app to calculate the future value of an investment using compound interest.

## 📌 Features

* Calculates total amount based on:

  * Principal amount
  * Interest rate
  * Time (in years)
* Input validation (prevents negative and invalid values)
* Displays result in **Indian Rupee (INR)** format
* Lightweight and easy to integrate into any webpage

---

## 🧮 Formula Used

The calculation is based on the compound interest formula:

```
A = P * (1 + r)^t
```

Where:

* `A` = Final amount
* `P` = Principal
* `r` = Annual interest rate (decimal)
* `t` = Time in years

---

## 📂 Project Structure

```
project-folder/
│── index.html
│── script.js
│── style.css (optional)
```

---

## 🚀 How to Use

1. Clone the repository:

```
git clone https://github.com/your-username/compound-interest-calculator.git
```

2. Open `index.html` in your browser.

3. Enter:

   * Principal amount
   * Interest rate (%)
   * Number of years

4. Click the **Calculate** button to see the result.

---

## 🧾 JavaScript Function

```javascript
function calculate(){
    const totalamount = document.getElementById("total-amount");
    const principalinput = document.getElementById("principal");
    const rateinput = document.getElementById("rate");
    const yearsinput = document.getElementById("years");

    let principal = Number(principalinput.value);
    let rate = Number(rateinput.value / 100);
    let years = Number(yearsinput.value);

    if(principal < 0 || isNaN(principal)){
        principal = 0;
        principalinput.value = 0;
    }

    if(rate < 0 || isNaN(rate)){
        rate = 0;
        rateinput.value = 0;
    }

    if(years < 0 || isNaN(years)){
        years = 0;
        yearsinput.value = 0;
    }

    const result = principal * Math.pow((1 + rate / 1), 1 * years);

    totalamount.textContent = result.toLocaleString(undefined, {
        style: "currency",
        currency: "INR"
    });
}
```

---

## ⚠️ Validation Rules

* Negative values are automatically reset to `0`
* Non-numeric inputs are handled safely
* Ensures calculation never breaks

---

## 🎯 Future Improvements

* Add monthly compounding option
* Add chart visualization
* Improve UI/UX design
* Add currency selector

---

## 📄 License

This project is open-source and free to use.

---

## 🙌 Contributing

Pull requests are welcome! Feel free to fork this repo and improve it.
