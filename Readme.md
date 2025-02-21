# Currency Converter

This project is a continuation of a previous WPF application built, which relied on static exchange rates. The new version enhances the functionality by allowing users to manage currencies and exchange rates dynamically through a database.

## Features

- **Currency Conversion** – Convert between different currencies using exchange rates stored in the database.
- **Currency Management** – Add, edit, and delete currencies and their exchange rates via the "Currency Master" tab.
- **Database Storage** – Stores currencies and rates in a local `.mdf` database file.
- **User-Friendly Interface** – Intuitive icons and layout for seamless interaction.
- **Validation** – Ensures only numeric input is accepted for currency amounts.

## Project Structure

The application consists of a single WPF window with two tabs:

1. **Converter** – The user inputs an amount, selects the source and target currency, and converts it.
2. **Currency Master** – The user can add new currencies with their rates, edit existing ones, or delete them from the database.

## Database Schema

The application uses a Microsoft SQL Server `.mdf` database with the following table:

```sql
CREATE TABLE [dbo].[Currency_Master] (
    [Id]           INT           IDENTITY (1, 1) NOT NULL,
    [Amount]       FLOAT (53)    NOT NULL,
    [CurrencyName] NVARCHAR (50) NOT NULL,
    PRIMARY KEY CLUSTERED ([Id] ASC)
);
```

## Configuration

The connection to the database is defined in the `App.config` file using a connection string. Ensure that the connection string is properly set up to match your database location and configuration.

## How to Run

1. **Open the solution in Visual Studio 2019 or later.**
2. **Ensure SQL Server LocalDB is installed on your system.**
3. **Check and modify the connection string in `App.config` if needed.**
4. **Build the project to restore the necessary packages.**
5. **Run the application.**

## Dependencies

- **.NET Framework 4.7.2**
- **SQL Server LocalDB**
- **Entity Framework for database interaction**

## Future Enhancements

- **Fetch real-time exchange rates from an external API.**
- **Enhance UI with additional styling and animations.**
- **Improve error handling and validation for database operations.**

## Notes

This project is an improved version of the original static currency converter and is intended for educational purposes. The exchange rates are stored in the database and can be modified by the user.

