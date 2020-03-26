---
title: Erstellen wiederverwendbarer UI-Komponenten mit Blazor
description: Erfahren Sie, wie Sie wiederverwendbare UI-Komponenten mit Blazor erstellen und mit ASP.NET Web Forms-Steuerelementen vergleichen.
author: danroth27
ms.author: daroth
ms.date: 09/18/2019
ms.openlocfilehash: 228f7aec4c7b87cb6d4127b55745f7a5ed90aaf9
ms.sourcegitcommit: b75a45f0cfe012b71b45dd9bf723adf32369d40c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/24/2020
ms.locfileid: "80228629"
---
# <a name="build-reusable-ui-components-with-blazor"></a>Erstellen wiederverwendbarer UI-Komponenten mit Blazor

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

Eines der schönsten Dinge an ASP.NET Web Forms ist, wie es die Verkapselung von wiederverwendbaren Teilen von Benutzeroberflächencode in wiederverwendbare UI-Steuerelemente ermöglicht. Benutzerdefinierte Benutzersteuerelemente können in Markup mithilfe von *.ascx-Dateien* definiert werden. Sie können auch ausgeklügelte Serversteuerelemente in Code mit vollständiger Designerunterstützung erstellen.

Blazor unterstützt auch die UI-Kapselung durch *Komponenten*. Eine Komponente:

- Ein eigenständiger Teil der Benutzeroberfläche.
- Behält seinen eigenen Status und seine Renderinglogik bei.
- Kann UI-Ereignishandler definieren, an Eingabedaten binden und seinen eigenen Lebenszyklus verwalten.
- Wird in der Regel in einer *.razor-Datei* mit Razor-Syntax definiert.

## <a name="an-introduction-to-razor"></a>Eine Einführung in Razor

Razor ist eine leichtgewichtige Markup-Tempor-Sprache, die auf HTML und C- basiert. Mit Razor können Sie nahtlos zwischen Markup und C-Code wechseln, um die Renderlogik Ihrer Komponente zu definieren. Wenn die *.razor-Datei* kompiliert wird, wird die Renderinglogik strukturiert in einer .NET-Klasse erfasst. Der Name der kompilierten Klasse wird dem *.razor-Dateinamen* entnommen. Der Namespace wird aus dem Standardnamespace für das Projekt und den Ordnerpfad `@namespace` entnommen, oder Sie können den Namespace mithilfe der Direktive explizit angeben (mehr zu Razor-Direktiven unten).

Die Renderinglogik einer Komponente wird mit normalem HTML-Markup erstellt, wobei die dynamische Logik mit c' hinzugefügt wird. Das `@` Zeichen wird für den Übergang zu C- verwendet. Razor ist in der Regel intelligent, wenn Sie wieder zu HTML gewechselt haben. Die folgende Komponente rendert `<p>` z. B. ein Tag mit der aktuellen Uhrzeit:

```razor
<p>@DateTime.Now</p>
```

Um explizit den Anfang und die Endung eines C-Ausdrucks anzugeben, verwenden Sie Klammern:

```razor
<p>@(DateTime.Now)</p>
```

Razor erleichtert auch die Verwendung des Steuerungsflusses von C- in Ihrer Renderinglogik. Sie können z. B. einige HTML-Codes bedingt wie folgt rendern:

```razor
@if (value % 2 == 0)
{
    <p>The value was even.</p>
}
```

Sie können auch eine Liste von Elementen `foreach` generieren, die eine normale C-Schleife wie folgt verwenden:

```razor
<ul>
@foreach (var item in items)
{
    <li>@item.Text</li>
}
</ul>
```

Razor-Direktiven, wie Direktiven in ASP.NET Web Forms, steuern viele Aspekte, wie eine Razor-Komponente kompiliert wird. Beispiele hierfür sind die Komponenten:

- Namespace
- Basisklasse
- Implementierte Schnittstellen
- Generische Parameter
- Importierte Namespaces
- Routen

Razor-Direktiven `@` beginnen mit dem Zeichen und werden in der Regel am Anfang einer neuen Zeile am Anfang der Datei verwendet. Die `@namespace` Direktive definiert z. B. den Namespace der Komponente:

```razor
@namespace MyComponentNamespace
```

In der folgenden Tabelle werden die verschiedenen Razor-Direktiven zusammengefasst, die in Blazor verwendet werden, sowie deren ASP.NET Web Forms-Äquivalente, sofern vorhanden.

|Direktive    |BESCHREIBUNG|Beispiel|Web Forms-Äquivalent|
|-------------|-----------|-------|--------------------|
|`@attribute` |Fügt der Komponente ein Attribut auf Klassenebene hinzu|`@attribute [Authorize]`|Keine|
|`@code`      |Fügt der Komponente Klassenmember hinzu|`@code { ... }`|`<script runat="server">...</script>`|
|`@implements`|Implementiert die angegebene Schnittstelle|`@implements IDisposable`|Verwenden des CodeBehinds|
|`@inherits`  |Erbt von der angegebenen Basisklasse|`@inherits MyComponentBase`|`<%@ Control Inherits="MyUserControlBase" %>`|
|`@inject`    |Injiziert einen Dienst in die Komponente|`@inject IJSRuntime JS`|Keine|
|`@layout`    |Gibt eine Layoutkomponente für die Komponente an|`@layout MainLayout`|`<%@ Page MasterPageFile="~/Site.Master" %>`|
|`@namespace` |Legt den Namespace für die Komponente fest|`@namespace MyNamespace`|Keine|
|`@page`      |Gibt die Route für die Komponente an|`@page "/product/{id}"`|`<%@ Page %>`|
|`@typeparam` |Gibt einen generischen Typparameter für die Komponente an.|`@typeparam TItem`|Verwenden des CodeBehinds|
|`@using`     |Gibt einen Namespace an, der in den Bereich eingebracht werden soll.|`@using MyComponentNamespace`|Hinzufügen von Namespace in *web.config*|

Razor-Komponenten verwenden außerdem umfangreiche *Direktivenattribute* für Elemente, um verschiedene Aspekte der Kompilierung von Komponenten zu steuern (Ereignisbehandlung, Datenbindung, Komponenten- & Elementreferenzen usw.). Direktive-Attribute folgen alle einer allgemeinen generischen Syntax, bei der die Werte in Klammern optional sind:

```razor
@directive(-suffix(:name))(="value")
```

In der folgenden Tabelle werden die verschiedenen Attribute für Razor-Direktiven zusammengefasst, die in Blazor verwendet werden.

|Attribut    |BESCHREIBUNG|Beispiel|
|-------------|-----------|-------|
|`@attributes`|Rendert ein Wörterbuch mit Attributen|`<input @attributes="ExtraAttributes" />`|
|`@bind`      |Erstellt eine zweiseitige Datenbindung    |`<input @bind="username" @bind:event="oninput" />`|
|`@on{event}` |Fügt einen Ereignishandler für das angegebene Ereignis hinzu|`<button @onclick="IncrementCount">Click me!</button>`|
|`@key`       |Gibt einen Schlüssel an, der vom Diffingalgorithmus zum Beibehalten von Elementen in einer Auflistung verwendet werden soll.|`<DetailsEditor @key="person" Details="person.Details" />`|
|`@ref`       |Erfasst einen Verweis auf die Komponente oder das HTML-Element|`<MyDialog @ref="myDialog" />`|

Die verschiedenen Direktivenattribute,`@onclick`die `@bind` `@ref`von Blazor ( , , usw.) verwendet werden, werden in den folgenden Abschnitten und späteren Kapiteln behandelt.

Viele der Syntaxen, die in *.aspx-* und *.ascx-Dateien* verwendet werden, weisen parallele Syntaxen in Razor auf. Im Folgenden finden Sie einen einfachen Vergleich der Syntaxen für ASP.NET Web Forms und Razor.

|Funktion                      |Web Forms           |Syntax               |Razor         |Syntax |
|-----------------------------|--------------------|---------------------|--------------|-------|
|Anweisungen                   |`<%@ [directive] %>`|`<%@ Page %>`        |`@[directive]`|`@page`|
|Codeblöcke                  |`<% %>`             |`<% int x = 123; %>` |`@{ }`        |`@{ int x = 123; }`|
|Ausdrücke<br>(HTML-kodiert)|`<%: %>`            |`<%:DateTime.Now %>` |Implizite:`@`<br>explizit:`@()`|`@DateTime.Now`<br>`@(DateTime.Now)`|
|Kommentare                     |`<%-- --%>`         |`<%-- Commented --%>`|`@* *@`       |`@* Commented *@`|
|Datenbindung                 |`<%# %>`            |`<%# Bind("Name") %>`|`@bind`       |`<input @bind="username" />`|

Um der Razor-Komponentenklasse Member `@code` hinzuzufügen, verwenden Sie die Direktive. Diese Technik ähnelt der `<script runat="server">...</script>` Verwendung eines Blocks in einem ASP.NET Web Forms-Benutzersteuerelement oder einer Seite.

```razor
@code {
    int count = 0;

    void IncrementCount()
    {
        count++;
    }
}
```

Da Razor auf C-Code basiert, muss es aus einem C-Projekt kompiliert werden (*.csproj*). Sie können *.razor-Dateien* nicht aus einem Visual Basic-Projekt kompilieren (*.vbproj*). Sie können weiterhin auf Visual Basic-Projekte aus Ihrem Blazor-Projekt verweisen. Auch das Gegenteil ist der Fall.

Eine vollständige Razor-Syntaxreferenz finden Sie unter [Razor-Syntaxreferenz für ASP.NET Core](/aspnet/core/mvc/views/razor).

## <a name="use-components"></a>Verwenden von Komponenten

Neben normalem HTML können Komponenten auch andere Komponenten als Teil ihrer Renderinglogik verwenden. Die Syntax für die Verwendung einer Komponente in Razor ähnelt der Verwendung eines Benutzersteuerelements in einer ASP.NET Web Forms-App. Komponenten werden mithilfe eines Element-Tags angegeben, das mit dem Typnamen der Komponente übereinstimmt. Sie können z. `Counter` B. eine Komponente wie die folgende hinzufügen:

```razor
<Counter />
```

Im Gegensatz zu ASP.NET Web Forms, Komponenten in Blazor:

- Verwenden Sie kein Elementpräfix (z. B. `asp:`).
- Erfordern Sie keine Registrierung auf der Seite oder in der *web.config*.

Denken Sie an Razor-Komponenten wie .NET-Typen, denn genau das sind sie. Wenn auf die Baugruppe verwiesen wird, auf die die Komponente verweist, steht die Komponente zur Verwendung zur Verfügung. Um den Namespace der Komponente in `@using` den Anwendungsbereich zu bringen, wenden Sie die Direktive an:

```razor
@using MyComponentLib

<Counter />
```

Wie in den standardmäßigen Blazor-Projekten gesehen, ist es üblich, Direktiven in eine `@using` *_Imports.razor-Datei* zu setzen, so dass sie in alle *.razor-Dateien* im selben Verzeichnis und in untergeordneten Verzeichnissen importiert werden.

Wenn sich der Namespace für eine Komponente nicht im Gültigkeitsbereich befindet, können Sie eine Komponente mit ihrem vollständigen Typnamen angeben, wie Sie dies in C':

```razor
<MyComponentLib.Counter />
```

## <a name="component-parameters"></a>Komponentenparameter

In ASP.NET Web Forms können Sie Parameter und Daten mithilfe öffentlicher Eigenschaften an Steuerelemente weiterfließen lassen. Diese Eigenschaften können in Markup mithilfe von Attributen oder direkt im Code festgelegt werden. Blazor-Komponenten funktionieren auf ähnliche Weise, obwohl die Komponenteneigenschaften ebenfalls mit dem `[Parameter]` Attribut gekennzeichnet werden müssen, das als Komponentenparameter betrachtet werden soll.

Die `Counter` folgende Komponente definiert einen `IncrementAmount` Komponentenparameter namens, der verwendet `Counter` werden kann, um den Betrag anzugeben, der bei jedem Klicken auf die Schaltfläche erhöht werden soll.

```razor
<h1>Counter</h1>

<p>Current count: @currentCount</p>

<button class="btn btn-primary" @onclick="IncrementCount">Click me</button>

@code {
    int currentCount = 0;

    [Parameter]
    public int IncrementAmount { get; set; } = 1;

    void IncrementCount()
    {
        currentCount+=IncrementAmount;
    }
}
```

Um einen Komponentenparameter in Blazor anzugeben, verwenden Sie ein Attribut wie in ASP.NET Web Forms:

```razor
<Counter IncrementAmount="10" />
```

## <a name="event-handlers"></a>Ereignishandler

Sowohl ASP.NET Web Forms als auch Blazor bieten ein ereignisbasiertes Programmiermodell für die Behandlung von UI-Ereignissen. Beispiele für solche Ereignisse sind Schaltflächenklicks und Texteingabe. In ASP.NET Web Forms verwenden Sie HTML-Serversteuerelemente, um UI-Ereignisse zu verarbeiten, die vom DOM verfügbar gemacht werden, oder Sie können Ereignisse verarbeiten, die von Webserversteuerelementen verfügbar gemacht werden. Die Ereignisse werden auf dem Server über Formular-Post-Back-Anforderungen angezeigt. Betrachten Sie die folgende Web Forms Schaltfläche klicken Beispiel:

*Counter.ascx*

```aspx-csharp
<asp:Button ID="ClickMeButton" runat="server" Text="Click me!" OnClick="ClickMeButton_Click" />
```

*Counter.ascx.cs*

```csharp
public partial class Counter : System.Web.UI.UserControl
{
    protected void ClickMeButton_Click(object sender, EventArgs e)
    {
        Console.WriteLine("The button was clicked!");
    }
}
```

In Blazor können Sie Handler für DOM-UI-Ereignisse direkt `@on{event}`mithilfe von Direktivenattributen des Formulars registrieren. Der `{event}` Platzhalter stellt den Namen des Ereignisses dar. Sie können z. B. auf Schaltflächenklicks wie folgt hören:

```razor
<button @onclick="OnClick">Click me!</button>

@code {
    void OnClick()
    {
        Console.WriteLine("The button was clicked!);
    }
}
```

Ereignishandler können ein optionales, ereignisspezifisches Argument akzeptieren, um weitere Informationen zum Ereignis bereitzustellen. Mausereignisse können z. `MouseEventArgs` B. ein Argument annehmen, es ist jedoch nicht erforderlich.

```razor
<button @onclick="OnClick">Click me!</button>

@code {
    void OnClick(MouseEventArgs e)
    {
        Console.WriteLine($"Mouse clicked at {e.ScreenX}, {e.ScreenY}.");
    }
}
```

Anstatt auf eine Methodengruppe für einen Ereignishandler zu verweisen, können Sie einen Lambda-Ausdruck verwenden. Mit einem Lambda-Ausdruck können Sie andere Werte im Gültigkeitsbereich schließen.

```razor
@foreach (var buttonLabel in buttonLabels)
{
    <button @onclick="() => Console.WriteLine($"The {buttonLabel} button was clicked!")">@buttonLabel</button>
}
```

Ereignishandler können synchron oder asynchron ausgeführt werden. Der folgende `OnClick` Ereignishandler wird z. B. asynchron ausgeführt:

```razor
<button @onclick="OnClick">Click me!</button>

@code {
    async Task OnClick()
    {
        var result = await Http.GetAsync("api/values");
    }
}
```

Nachdem ein Ereignis behandelt wurde, wird die Komponente gerendert, um alle Komponentenstatusänderungen zu berücksichtigen. Bei asynchronen Ereignishandlern wird die Komponente unmittelbar nach Abschluss der Handlerausführung gerendert. Die Komponente wird *nach* Abschluss der `Task` Asynchronität wieder gerendert. Dieser asynchrone Ausführungsmodus bietet die Möglichkeit, eine `Task` geeignete Benutzeroberfläche zu rendern, während die asynchrone noch ausgeführt wird.

```razor
<button @onclick="ShowMessage">Get message</button>

@if (showMessage)
{
    @if (message == null)
    {
        <p><em>Loading...</em></p>
    }
    else
    {
        <p>The message is: @message</p>
    }
}

@code
{
    bool showMessage = false;
    string message;

    public async Task ShowMessage()
    {
        showMessage = true;
        message = await MessageService.GetMessageAsync();
    }
}
```

Komponenten können auch ihre eigenen Ereignisse definieren, `EventCallback<TValue>`indem sie einen Komponentenparameter vom Typ definieren. Ereignisrückrufe unterstützen alle Variationen von DOM UI-Ereignishandlern: optionale Argumente, synchron ezielle oder asynchrone, Methodengruppen oder Lambda-Ausdrücke.

```razor
<button class="btn btn-primary" @onclick="OnClick">Click me!</button>

@code {
    [Parameter]
    public EventCallback<MouseEventArgs> OnClick { get; set; }
}
```

## <a name="data-binding"></a>Datenbindung

Blazor bietet einen einfachen Mechanismus zum Binden von Daten aus einer UI-Komponente an den Zustand der Komponente. Dieser Ansatz unterscheidet sich von den Features in ASP.NET Web Forms zum Binden von Daten aus Datenquellen an UI-Steuerelemente. Im Abschnitt [Umgang mit Daten](data.md) werden die Handhabung von Daten aus verschiedenen Datenquellen behandelt.

Um eine bidirektionade Datenbindung von einer UI-Komponente in `@bind` den Zustand der Komponente zu erstellen, verwenden Sie das Direktive-Attribut. Im folgenden Beispiel ist der Wert des Kontrollkästchens an das `isChecked` Feld gebunden.

```razor
<input type="checkbox" @bind="isChecked" />

@code {
    bool isChecked;
}
```

Wenn die Komponente gerendert wird, wird der Wert `isChecked` des Kontrollkästchens auf den Wert des Felds festgelegt. Wenn der Benutzer das Kontrollkästchen umschaltet, wird `onchange` `isChecked` das Ereignis ausgelöst, und das Feld wird auf den neuen Wert festgelegt. Die `@bind` Syntax in diesem Fall entspricht dem folgenden Markup:

```razor
<input value="@isChecked" @onchange="(UIChangeEventArgs e) => isChecked = e.Value" />
```

Um das für die Bindung verwendete `@bind:event` Ereignis zu ändern, verwenden Sie das Attribut.

```razor
<input @bind="text" @bind:event="oninput" />
<p>@text</p>

@code {
    string text;
}
```

Komponenten können auch die Datenbindung an ihre Parameter unterstützen. Um Daten bindung, definieren Sie einen Ereignisrückrufparameter mit demselben Namen wie der bindbare Parameter. Das Suffix "Geändert" wird dem Namen hinzugefügt.

*PasswordBox.razor*

```razor
Password: <input
    value="@Password"
    @oninput="OnPasswordChanged"
    type="@(showPassword ? "text" : "password")" />

<label><input type="checkbox" @bind="showPassword" />Show password</label>

@code {
    private bool showPassword;

    [Parameter]
    public string Password { get; set; }

    [Parameter]
    public EventCallback<string> PasswordChanged { get; set; }

    private Task OnPasswordChanged(ChangeEventArgs e)
    {
        Password = e.Value.ToString();
        return PasswordChanged.InvokeAsync(Password);
    }
}
```

Um eine Datenbindung an ein zugrunde liegendes UI-Element zu verketten, legen `@bind` Sie den Wert fest, und behandeln Sie das Ereignis direkt im UI-Element, anstatt das Attribut zu verwenden.

Um eine Bindung an einen `@bind-{Parameter}` Komponentenparameter zu verwenden, verwenden Sie ein Attribut, um den Parameter anzugeben, an den Sie binden möchten.

```razor
<PasswordBox @bind-Password="password" />

@code {
    string password;
}
```

## <a name="state-changes"></a>Zustandsänderungen

Wenn sich der Status der Komponente außerhalb eines normalen UI-Ereignisses oder Ereignisrückrufs geändert hat, muss die Komponente manuell signalisieren, dass sie erneut gerendert werden muss. Um zu signalisieren, dass sich der `StateHasChanged` Status einer Komponente geändert hat, rufen Sie die Methode für die Komponente auf.

Im folgenden Beispiel zeigt eine Komponente `AppState` eine Nachricht von einem Dienst an, die von anderen Teilen der App aktualisiert werden kann. Die Komponente registriert `StateHasChanged` ihre `AppState.OnChange` Methode bei dem Ereignis, sodass die Komponente gerendert wird, wenn die Nachricht aktualisiert wird.

```csharp
public class AppState
{
    public string Message { get; }

    // Lets components receive change notifications
    public event Action OnChange;

    public void UpdateMessage(string message)
    {
        shortlist.Add(itinerary);
        NotifyStateChanged();
    }

    private void NotifyStateChanged() => OnChange?.Invoke();
}
```

```razor
@inject AppState AppState

<p>App message: @AppState.Message</p>

@code {
    protected override void OnInitialized()
    {
        AppState.OnChange += StateHasChanged
    }
}
```

## <a name="component-lifecycle"></a>Komponentenlebenszyklus

Das ASP.NET Web Forms-Framework verfügt über klar definierte Lebenszyklusmethoden für Module, Seiten und Steuerelemente. Das folgende Steuerelement implementiert beispielsweise Ereignishandler `Init`für `Load`die `UnLoad` Ereignisse , und Lifecycle:

*Counter.ascx.cs*

```csharp
public partial class Counter : System.Web.UI.UserControl
{
    protected void Page_Init(object sender, EventArgs e) { ... }
    protected void Page_Load(object sender, EventArgs e) { ... }
    protected void Page_UnLoad(object sender, EventArgs e) { ... }
}
```

Blazor-Komponenten haben auch einen genau definierten Lebenszyklus. Der Lebenszyklus einer Komponente kann verwendet werden, um den Komponentenstatus zu initialisieren und erweitertes Komponentenverhalten zu implementieren.

Alle Komponentenlebenszyklusmethoden von Blazor verfügen sowohl über synchrone als auch über asynchrone Versionen. Das Komponentenrendering ist synchron. Sie können keine asynchrone Logik als Teil des Komponentenrenderings ausführen. Alle asynchronen Logiken müssen `async` als Teil einer Lebenszyklusmethode ausgeführt werden.

### <a name="oninitialized"></a>Oninitialized

Die `OnInitialized` `OnInitializedAsync` und Methoden werden verwendet, um die Komponente zu initialisieren. Eine Komponente wird in der Regel initialisiert, nachdem sie zum ersten Mal gerendert wurde. Nachdem eine Komponente initialisiert wurde, kann sie mehrmals gerendert werden, bevor sie schließlich verworfen wird. Die `OnInitialized` Methode ähnelt `Page_Load` dem Ereignis in ASP.NET Web Forms-Seiten und -Steuerelementen.

```csharp
protected override void OnInitialized() { ... }
protected override async Task OnInitializedAsync() { await ... }
```

### <a name="onparametersset"></a>OnParametersSet

Die `OnParametersSet` `OnParametersSetAsync` und-Methoden werden aufgerufen, wenn eine Komponente Parameter von ihrem übergeordneten Element empfangen hat und der Wert Eigenschaften zugewiesen ist. Diese Methoden werden nach der Komponenteninitialisierung und *bei jeder Gerederung der Komponente*ausgeführt.

```csharp
protected override void OnParametersSet() { ... }
protected override async Task OnParametersSetAsync() { await ... }
```

### <a name="onafterrender"></a>OnAfterRender

Die `OnAfterRender` `OnAfterRenderAsync` und-Methoden werden aufgerufen, nachdem eine Komponente das Rendern abgeschlossen hat. Element- und Komponentenreferenzen werden an dieser Stelle aufgefüllt (mehr zu diesen Konzepten unten). Die Interaktivität mit dem Browser ist an dieser Stelle aktiviert. Interaktionen mit der DOM- und JavaScript-Ausführung können sicher stattfinden.

```csharp
protected override void OnAfterRender(bool firstRender)
{
    if (firstRender)
    {
        ...
    }
}
protected override async Task OnAfterRenderAsync(bool firstRender)
{
    if (firstRender)
    {
        await ...
    }
}
```

`OnAfterRender`und `OnAfterRenderAsync` *werden beim Vorrendern auf dem Server nicht aufgerufen.*

Der `firstRender` Parameter `true` ist das erste Mal, dass die Komponente gerendert wird. Andernfalls ist `false`sein Wert .

### <a name="idisposable"></a>IDisposable

Blazor-Komponenten `IDisposable` können implementiert werden, um Ressourcen zu entsorgen, wenn die Komponente aus der Benutzeroberfläche entfernt wird. Eine Razor-Komponente `IDispose` kann `@implements` mithilfe der Direktive implementiert werden:

```razor
@using System
@implements IDisposable

...

@code {
    public void Dispose()
    {
        ...
    }
}
```

## <a name="capture-component-references"></a>Capture-Komponentenreferenzen

In ASP.NET Web Forms ist es üblich, eine Steuerelementinstanz direkt im Code zu bearbeiten, indem auf ihre ID verwiesen wird. In Blazor ist es auch möglich, einen Verweis auf eine Komponente zu erfassen und zu manipulieren, obwohl er viel seltener ist.

Um einen Komponentenverweis in Blazor `@ref` zu erfassen, verwenden Sie das Direktive-Attribut. Der Wert des Attributs sollte mit dem Namen eines festsetzbaren Felds mit demselben Typ wie die referenzierte Komponente übereinstimmen.

```razor
<MyLoginDialog @ref="loginDialog" ... />

@code {
    MyLoginDialog loginDialog;

    void OnSomething()
    {
        loginDialog.Show();
    }
}
```

Wenn die übergeordnete Komponente gerendert wird, wird das Feld mit der untergeordneten Komponenteninstanz aufgefüllt. Anschließend können Sie Methoden auf der Komponenteninstanz aufrufen oder anderweitig bearbeiten.

Das Bearbeiten des Komponentenstatus direkt mithilfe von Komponentenreferenzen wird nicht empfohlen. Dadurch wird verhindert, dass die Komponente automatisch zum richtigen Zeitpunkt gerendert wird.

## <a name="capture-element-references"></a>Erfassen von Elementreferenzen

Blazor-Komponenten können Verweise auf ein Element erfassen. Im Gegensatz zu HTML-Serversteuerelementen in ASP.NET Web Forms können Sie das DOM nicht direkt mithilfe eines Elementverweises in Blazor bearbeiten. Blazor verarbeitet die meisten DOM-Interaktionen für Sie mit seinem DOM-Diffing-Algorithmus. Erfasste Elementverweise in Blazor sind undurchsichtig. Sie werden jedoch verwendet, um einen bestimmten Elementverweis in einem JavaScript-Interopaufruf zu übergeben. Weitere Informationen zu JavaScript-Interop finden Sie [unter ASP.NET Core Blazor JavaScript interop](/aspnet/core/blazor/javascript-interop).

## <a name="templated-components"></a>Komponenten mit Vorlagen

In ASP.NET Web Forms können Sie *Vorlagensteuerelemente*erstellen. Vorlagensteuerelemente ermöglichen es dem Entwickler, einen Teil des HTML-Codes anzugeben, der zum Rendern eines Containersteuerelements verwendet wird. Die Mechanismen zum Erstellen von Serversteuerelementen mit Vorlagen sind komplex, ermöglichen jedoch leistungsstarke Szenarien zum benutzerdefinierten Rendern von Daten. Beispiele für Vorlagensteuerelemente sind `Repeater` und `DataList`.

Blazor-Komponenten können auch vorlagen, indem `RenderFragment` Komponentenparameter vom Typ oder `RenderFragment<T>`definiert werden. A `RenderFragment` stellt einen Teil des Razor-Markups dar, das dann von der Komponente gerendert werden kann. A `RenderFragment<T>` ist ein Teil des Razor-Markups, das einen Parameter annimmt, der angegeben werden kann, wenn das Renderfragment gerendert wird.

### <a name="child-content"></a>Kinderinhalte

Blazor-Komponenten können ihren untergeordneten Inhalt als untergeordneten `RenderFragment` Inhalt erfassen und diesen Inhalt als Teil des Komponentenrenderings rendern. Um untergeordnete nädenlegenden Inhalt `RenderFragment` zu `ChildContent`erfassen, definieren Sie einen Komponentenparameter des Typs, und benennen Sie ihn .

*ChildContentComponent.razor*

```razor
<h1>Component with child content</h1>

<div>@ChildContent</div>

@code {
    [Parameter]
    public RenderFragment ChildContent { get; set; }
}
```

Eine übergeordnete Komponente kann dann untergeordneten Inhalt mithilfe der normalen Razor-Syntax bereitstellen.

```razor
<ChildContentComponent>
    <p>The time is @DateTime.Now</p>
</ChildContentComponent>
```

### <a name="template-parameters"></a>Vorlagenparameter

Eine Blazor-Komponente mit Vorlagen kann auch `RenderFragment` `RenderFragment<T>`mehrere Komponentenparameter vom Typ oder definieren. Der Parameter `RenderFragment<T>` für a kann angegeben werden, wenn er aufgerufen wird. Um einen generischen Typparameter für `@typeparam` eine Komponente anzugeben, verwenden Sie die Razor-Direktive.

*SimpleListView.razor*

```razor
@typeparam TItem

@Heading

<ul>
@foreach (var item in Items)
{
    <li>@ItemTemplate(item)</li>
}
</ul>

@code {
    [Parameter]
    public RenderFragment Heading { get; set; }

    [Parameter]
    public RenderFragment<TItem> ItemTemplate { get; set; }

    [Parameter]
    public IEnumerable<TItem> Items { get; set; }
}
```

Bei Verwendung einer Vorlagenkomponente können die Vorlagenparameter mithilfe untergeordneter Elemente angegeben werden, die den Namen der Parameter entsprechen. Komponentenargumente vom `RenderFragment<T>` Typ, der als `context`Elemente übergeben wird, haben einen impliziten Parameter mit dem Namen . Sie können den Namen dieses Implement-Parameters mithilfe des `Context` Attributs für das untergeordnete Element ändern. Alle generischen Typparameter können mithilfe eines Attributs angegeben werden, das mit dem Namen des Typparameters übereinstimmt. Der Typparameter wird nach Möglichkeit abgeleitet:

```razor
<SimpleListView Items="messages" TItem="string">
    <Heading>
        <h1>My list</h1>
    </Heading>
    <ItemTemplate Content="message">
        <p>The message is: @message</p>
    </ItemTemplate>
</SimpleListView>
```

Die Ausgabe dieser Komponente sieht wie folgt aus:

```html
<h1>My list</h1>
<ul>
    <li>The message is: message1</li>
    <li>The message is: message2</li>
<ul>
```

## <a name="code-behind"></a>CodeBehind

Eine Blazor-Komponente wird in der Regel in einer einzelnen *.razor-Datei* erstellt. Es ist jedoch auch möglich, Code und Markup mithilfe einer CodeBehind-Datei zu trennen. Um eine Komponentendatei zu verwenden, fügen Sie eine C-Datei hinzu, die mit dem Dateinamen der Komponentendatei übereinstimmt, jedoch mit einer *hinzugefügten .cs-Erweiterung* (*Counter.razor.cs*hinzugefügt wurde). Verwenden Sie die C-Datei, um eine Basisklasse für die Komponente zu definieren. Sie können die Basisklasse nach Bekunden benennen, aber es ist üblich, die Klasse wie `Base` die`CounterBase`Komponentenklasse zu benennen, jedoch mit einer zusätzlichen Erweiterung ( ). Die komponentenbasierte Klasse muss ebenfalls `ComponentBase`von stammen. Fügen Sie dann in der `@inherits` Razor-Komponentendatei die Direktive`@inherits CounterBase`hinzu, um die Basisklasse für die Komponente ( anzugeben).

*Counter.razor*

```razor
@inherits CounterBase

<h1>Counter</h1>

<p>Current count: @currentCount</p>

<button @onclick="IncrementCount">Click me</button>
```

*Counter.razor.cs*

```csharp
public class CounterBase : ComponentBase
{
    protected int currentCount = 0;

    protected void IncrementCount()
    {
        currentCount++;
    }
}
```

Die Sichtbarkeit der Komponentenmember in der Basisklasse muss für die Komponentenklasse sichtbar sein `protected` oder `public` sichtbar sein.

## <a name="additional-resources"></a>Zusätzliche Ressourcen

Die vorhergehende ist nicht eine erschöpfende Behandlung aller Aspekte von Blazor Komponenten. Weitere Informationen zum [Erstellen und Verwenden ASP.NET Core Razor-Komponenten](/aspnet/core/blazor/components)finden Sie in der Blazor-Dokumentation.

>[!div class="step-by-step"]
>[VorherigeS](app-startup.md)
>[Weiter](pages-routing-layouts.md)
