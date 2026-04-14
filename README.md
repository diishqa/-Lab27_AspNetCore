# Знакомство с ASP.NET Core:
первый веб-сервер на C#
## Кузьмина Диана Александровна
## ИСП-232
___
**Цель работы:** Установить .NET SDK и настроить проект в VS Code. Понять, что
такое HTTP-запрос и HTTP-ответ. Создать минимальный веб-сервер на ASP.NET Core.
Разобраться с маршрутизацией и middleware.

Представьте, что ваша WPF-программа не показывает окно, а ждёт, пока кто-то
напишет ей через интернет. Когда браузер заходит на адрес http://localhost:5000/, он как
раз «пишет» вашей программе. Она отвечает — и браузер показывает ответ. Это и есть
веб-сервер.
___
| Характеристика | Пример кода |
|----------------|--------------|
| **Создание сервера** | WebApplication.CreateBuilder() |
| **Запуск** | app.Run() |
| **Маршрут GET** | app.MapGet("/", () => "Hello World") |
| **Параметр маршрута** | app.MapGet("/user/{name}", (string name) => $"Hello {name}") |
| **Возврат JSON** | return new { Id = 1, Name = "John" }return Results.Ok(new { Id = 1 }) |
| **Middleware** | app.Use(async (ctx, next) => { await next(); }) |
| **Логирование** | Встроенное логирование: app.Logger.LogInformation("...")Console.WriteLine("...") |
| **Статус ответа** | return Results.NotFound()return Results.BadRequest() |
| **Тип данных** | Строгие типы:public record User(int Id, string Name)public class Product { ... } |