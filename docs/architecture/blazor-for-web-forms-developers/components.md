---
title: Erstellen wiederverwendbarer Benutzeroberflächen Komponenten mit blazor
description: Erfahren Sie, wie Sie wiederverwendbare UI-Komponenten mit blazor erstellen und wie Sie mit ASP.net-Web Forms Steuerelementen vergleichen.
author: danroth27
ms.author: daroth
ms.date: 09/18/2019
ms.openlocfilehash: 1a5f6b63143c4fd7a276219b9c4877e9e355c996
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/13/2020
ms.locfileid: "83378317"
---
# <a name="build-reusable-ui-components-with-blazor"></a>Erstellen wiederverwendbarer Benutzeroberflächen Komponenten mit blazor

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

Eine der schönen Aspekte von ASP.net Web Forms ist, wie Sie wiederverwendbare Elemente von Benutzeroberflächen Code in wiederverwendbare UI-Steuerelemente einkapseln kann. Benutzerdefinierte Benutzer Steuerelemente können mithilfe von *ASCX* -Dateien im Markup definiert werden. Mit vollständiger Designer Unterstützung können Sie auch aufwändige Server Steuerelemente im Code erstellen.

Blazor unterstützt auch die Benutzeroberflächen Kapselung durch- *Komponenten*. Eine Komponente:

- Bei handelt es sich um einen eigenständigen Block von Benutzeroberflächen.
- Behält seine eigene Zustands-und Renderinglogik bei.
- Kann Benutzeroberflächen-Ereignishandler definieren, an Eingabedaten binden und ihren eigenen Lebenszyklus verwalten.
- Wird in der Regel in einer *Razor* -Datei mit Razor-Syntax definiert.

## <a name="an-introduction-to-razor"></a>Eine Einführung in Razor

Razor ist eine einfache Markup Vorlagen Sprache, die auf HTML und c# basiert. Mit Razor können Sie nahtlos zwischen Markup und c#-Code wechseln, um die Komponenten Rendering-Logik zu definieren. Wenn die *Razor* -Datei kompiliert wird, wird die Renderinglogik auf strukturierte Weise in einer .NET-Klasse aufgezeichnet. Der Name der kompilierten Klasse stammt aus dem Namen der *Razor* -Datei. Der Namespace wird aus dem Standard Namespace für das Projekt und den Ordner Pfad entnommen, oder Sie können den Namespace mithilfe der-Anweisung explizit angeben `@namespace` (Weitere Informationen zu Razor-Direktiven finden Sie unten).

Die Renderinglogik einer Komponente wird mithilfe von normalem HTML-Markup mit dynamischer Logik erstellt, die mit c# hinzugefügt wurde. Das `@` Zeichen wird für den Übergang zu c# verwendet. Razor ist in der Regel intelligent, wenn Sie zu HTML zurück gewechselt haben. Die folgende Komponente rendert z. b. ein `<p>` Tag mit der aktuellen Uhrzeit:

```razor
<p>@DateTime.Now</p>
```

Um den Anfang und das Beenden eines c#-Ausdrucks explizit anzugeben, verwenden Sie Klammern:

```razor
<p>@(DateTime.Now)</p>
```

Razor erleichtert auch die Verwendung der c#-Ablauf Steuerung in ihrer Renderinglogik. Beispielsweise können Sie einige HTML-Code wie folgt bedingt darstellen:

```razor
@if (value % 2 == 0)
{
    <p>The value was even.</p>
}
```

Sie können auch eine Liste von Elementen generieren, indem Sie eine normale c#-Schleife wie die folgende verwenden `foreach` :

```razor
<ul>
@foreach (var item in items)
{
    <li>@item.Text</li>
}
</ul>
```

Razor-Direktiven, wie Direktiven in ASP.net-Web Forms, Steuern viele Aspekte der Kompilierung einer Razor-Komponente. Beispiele hierfür sind:

- Namespace
- Basisklasse
- Implementierte Schnittstellen
- Generische Parameter
- Importierte Namespaces
- Routen

Razor-Direktiven beginnen mit dem `@` Zeichen und werden in der Regel am Anfang einer neuen Zeile am Anfang der Datei verwendet. Die `@namespace` -Direktive definiert z. b. den-Namespace der Komponente:

```razor
@namespace MyComponentNamespace
```

In der folgenden Tabelle werden die verschiedenen Razor-Direktiven, die in blazor verwendet werden, und deren Web Forms ASP.NET-Entsprechungen zusammengefasst, sofern vorhanden

|Direktive    |Beschreibung|Beispiel|Web Forms Äquivalent|
|-------------|-----------|-------|--------------------|
|`@attribute` |Fügt der Komponente ein Attribut auf Klassenebene hinzu.|`@attribute [Authorize]`|Keine|
|`@code`      |Fügt der Komponente Klassenmember hinzu.|`@code { ... }`|`<script runat="server">...</script>`|
|`@implements`|Implementiert die angegebene Schnittstelle.|`@implements IDisposable`|Verwenden des CodeBehinds|
|`@inherits`  |Erbt von der angegebenen Basisklasse|`@inherits MyComponentBase`|`<%@ Control Inherits="MyUserControlBase" %>`|
|`@inject`    |Fügt einen Dienst in die Komponente ein.|`@inject IJSRuntime JS`|Keine|
|`@layout`    |Gibt eine Layoutkomponente für die Komponente an.|`@layout MainLayout`|`<%@ Page MasterPageFile="~/Site.Master" %>`|
|`@namespace` |Legt den Namespace für die Komponente fest.|`@namespace MyNamespace`|Keine|
|`@page`      |Gibt die Route für die Komponente an.|`@page "/product/{id}"`|`<%@ Page %>`|
|`@typeparam` |Gibt einen generischen Typparameter für die Komponente an.|`@typeparam TItem`|Verwenden des CodeBehinds|
|`@using`     |Gibt einen Namespace an, der in den Gültigkeitsbereich|`@using MyComponentNamespace`|Namespace in der Datei " *Web. config* " hinzufügen|

Razor-Komponenten machen außerdem eine umfassende Verwendung von *direktivenattributen* für Elemente, um verschiedene Aspekte der Kompilierung von Komponenten zu steuern (Ereignis Behandlung, Datenbindung, Verweise auf Komponenten & Elemente usw.). Direktivenattribute folgen allen allgemeinen generischen Syntax, bei der die Werte in Klammern optional sind:

```razor
@directive(-suffix(:name))(="value")
```

In der folgenden Tabelle werden die verschiedenen Attribute der in blazor verwendeten Razor-Direktiven zusammengefasst.

|attribute    |Beschreibung|Beispiel|
|-------------|-----------|-------|
|`@attributes`|Rendert ein Wörterbuch von Attributen.|`<input @attributes="ExtraAttributes" />`|
|`@bind`      |Erstellt eine bidirektionale Datenbindung.    |`<input @bind="username" @bind:event="oninput" />`|
|`@on{event}` |Fügt einen Ereignishandler für das angegebene Ereignis hinzu.|`<button @onclick="IncrementCount">Click me!</button>`|
|`@key`       |Gibt einen Schlüssel an, der vom diffingalgorithmus zum Beibehalten von Elementen in einer Auflistung verwendet werden soll.|`<DetailsEditor @key="person" Details="person.Details" />`|
|`@ref`       |Zeichnet einen Verweis auf die Komponente oder das HTML-Element auf.|`<MyDialog @ref="myDialog" />`|

Die verschiedenen von blazor ( `@onclick` ,, usw.) verwendeten Direktivenattribute `@bind` `@ref` werden in den Abschnitten unten und in späteren Kapiteln behandelt.

Viele der Syntaxen, die in *aspx* -und *ASCX* -Dateien verwendet werden, haben eine parallele Syntax in Razor. Im folgenden finden Sie einen einfachen Vergleich der Syntaxen für ASP.net Web Forms und Razor.

|Feature                      |Web Forms           |Syntax               |Razor         |Syntax |
|-----------------------------|--------------------|---------------------|--------------|-------|
|Anweisungen                   |`<%@ [directive] %>`|`<%@ Page %>`        |`@[directive]`|`@page`|
|Codeblöcke                  |`<% %>`             |`<% int x = 123; %>` |`@{ }`        |`@{ int x = 123; }`|
|Ausdrücke<br>(HTML-codiert)|`<%: %>`            |`<%:DateTime.Now %>` |Verzerrungen`@`<br>Explizite`@()`|`@DateTime.Now`<br>`@(DateTime.Now)`|
|Kommentare                     |`<%-- --%>`         |`<%-- Commented --%>`|`@* *@`       |`@* Commented *@`|
|Datenbindung                 |`<%# %>`            |`<%# Bind("Name") %>`|`@bind`       |`<input @bind="username" />`|

Verwenden Sie die-Direktive, um der Razor-Komponenten Klasse Elemente hinzuzufügen `@code` . Dieses Verfahren ähnelt der Verwendung eines `<script runat="server">...</script>` Blocks in einem ASP.net-Web Forms Benutzer Steuerelement oder einer Seite.

```razor
@code {
    int count = 0;

    void IncrementCount()
    {
        count++;
    }
}
```

Da Razor auf c# basiert, muss es in einem c#-Projekt (*. csproj*) kompiliert werden. *Razor* -Dateien können nicht aus einem Visual Basic Projekt (*vbproj*) kompiliert werden. Sie können weiterhin auf Visual Basic Projekte aus Ihrem blazor-Projekt verweisen. Das Gegenteil gilt auch für.

Eine vollständige Razor-Syntax Referenz finden Sie unter [Razor-Syntax Referenz für ASP.net Core](/aspnet/core/mvc/views/razor).

## <a name="use-components"></a>Verwenden von Komponenten

Abgesehen von normalem HTML können Komponenten auch andere Komponenten als Teil ihrer Renderinglogik verwenden. Die Syntax für die Verwendung einer Komponente in Razor ähnelt der Verwendung eines Benutzer Steuer Elements in einer ASP.net-Web Forms-app. Komponenten werden mithilfe eines Elementtags angegeben, das mit dem Typnamen der Komponente übereinstimmt. Beispielsweise können Sie eine-Komponente wie die folgende hinzufügen `Counter` :

```razor
<Counter />
```

Im Gegensatz zu ASP.net-Web Forms Komponenten in blazor:

- Verwenden Sie kein Element Präfix (z `asp:` . b.).
- Sie müssen nicht auf der Seite oder in der Datei " *Web. config*" registriert werden.

Stellen Sie sich die Razor-Komponenten wie .NET-Typen vor, denn das ist genau das, was Sie sind. Wenn auf die Assembly verwiesen wird, die die Komponente enthält, kann die Komponente verwendet werden. Um den Namespace der Komponente in den Gültigkeitsbereich zu bringen, wenden Sie die- `@using` Anweisung an

```razor
@using MyComponentLib

<Counter />
```

Wie in den standardmäßigen blazor-Projekten gezeigt, werden `@using` Direktiven häufig in eine *_Imports. Razor* -Datei eingefügt, sodass Sie in alle *Razor* -Dateien im gleichen Verzeichnis und in untergeordneten Verzeichnissen importiert werden.

Wenn sich der Namespace für eine Komponente nicht im Gültigkeitsbereich befindet, können Sie eine Komponente mit dem vollständigen Typnamen wie in c# angeben:

```razor
<MyComponentLib.Counter />
```

## <a name="component-parameters"></a>Komponentenparameter

In ASP.net Web Forms können Sie mithilfe öffentlicher Eigenschaften Parameter und Daten an Steuerelemente weitergeleitet. Diese Eigenschaften können in Markup mithilfe von Attributen festgelegt oder direkt im Code festgelegt werden. Blazor-Komponenten funktionieren in ähnlicher Weise, obwohl die Komponenteneigenschaften auch mit dem-Attribut gekennzeichnet werden müssen `[Parameter]` , um als Komponenten Parameter angesehen zu werden.

Die folgende `Counter` Komponente definiert einen Komponenten Parameter mit dem Namen `IncrementAmount` , der verwendet werden kann, um den Betrag anzugeben, der bei `Counter` jedem Klicken auf die Schaltfläche erhöht werden soll.

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

Um einen Komponenten Parameter in blazor anzugeben, verwenden Sie ein Attribut wie in ASP.net Web Forms:

```razor
<Counter IncrementAmount="10" />
```

## <a name="event-handlers"></a>Ereignishandler

Sowohl ASP.net Web Forms als auch blazor stellen ein Ereignis basiertes Programmiermodell für die Behandlung von Benutzeroberflächen Ereignissen bereit. Beispiele für derartige Ereignisse sind Schaltflächen Klicks und Texteingaben. In ASP.net Web Forms verwenden Sie HTML-Server Steuerelemente zur Handhabung von Benutzeroberflächen Ereignissen, die vom DOM verfügbar gemacht werden, oder Sie können Ereignisse behandeln, die von Webserver Steuerelementen verfügbar gemacht werden. Die Ereignisse werden auf dem Server über Formular-POST Back Anforderungen angezeigt. Beachten Sie die folgenden Web Forms Schaltflächen-Click-Beispiel:

*Counter. ascx*

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

In blazor können Sie Handler für DOM UI-Ereignisse direkt mithilfe von direktivenattributen im Formular registrieren `@on{event}` . Der `{event}` Platzhalter stellt den Namen des Ereignisses dar. Beispielsweise können Sie auf Schaltflächen Klicks wie folgt lauschen:

```razor
<button @onclick="OnClick">Click me!</button>

@code {
    void OnClick()
    {
        Console.WriteLine("The button was clicked!);
    }
}
```

Ereignishandler können ein optionales, Ereignis spezifisches Argument akzeptieren, um weitere Informationen zum Ereignis bereitzustellen. Mausereignisse können z. b. ein- `MouseEventArgs` Argument annehmen, aber es ist nicht erforderlich.

```razor
<button @onclick="OnClick">Click me!</button>

@code {
    void OnClick(MouseEventArgs e)
    {
        Console.WriteLine($"Mouse clicked at {e.ScreenX}, {e.ScreenY}.");
    }
}
```

Anstatt auf eine Methoden Gruppe für einen Ereignishandler zu verweisen, können Sie einen Lambda-Ausdruck verwenden. Ein Lambda-Ausdruck ermöglicht es Ihnen, andere Werte im Gültigkeitsbereich zu schließen.

```razor
@foreach (var buttonLabel in buttonLabels)
{
    <button @onclick="() => Console.WriteLine($"The {buttonLabel} button was clicked!")">@buttonLabel</button>
}
```

Ereignishandler können synchron oder asynchron ausgeführt werden. Der folgende Ereignishandler wird z. b. `OnClick` asynchron ausgeführt:

```razor
<button @onclick="OnClick">Click me!</button>

@code {
    async Task OnClick()
    {
        var result = await Http.GetAsync("api/values");
    }
}
```

Nachdem ein Ereignis behandelt wurde, wird die Komponente gerendert, um alle Änderungen des Komponenten Zustands zu berücksichtigen. Bei asynchronen Ereignis Handlern wird die Komponente unmittelbar nach Abschluss der handlerausführung gerendert. Die Komponente wird *wieder* gerendert, nachdem der asynchrone Vorgang `Task` abgeschlossen wurde. Dieser asynchrone Ausführungs Modus bietet die Möglichkeit, eine geeignete Benutzeroberfläche zu rendereinigen, während der asynchrone Vorgang `Task` noch ausgeführt wird.

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

Komponenten können auch eigene Ereignisse definieren, indem Sie einen Komponenten Parameter vom Typ definieren `EventCallback<TValue>` . Ereignis Rückrufe unterstützen alle Variationen von Dom UI-Ereignis Handlern: optionale Argumente, synchrone oder asynchrone Methoden, Methoden Gruppen oder Lambda-Ausdrücke.

```razor
<button class="btn btn-primary" @onclick="OnClick">Click me!</button>

@code {
    [Parameter]
    public EventCallback<MouseEventArgs> OnClick { get; set; }
}
```

## <a name="data-binding"></a>Datenbindung

Blazor stellt einen einfachen Mechanismus bereit, mit dem Daten aus einer Benutzeroberflächen Komponente an den Status der Komponente gebunden werden können. Diese Vorgehensweise unterscheidet sich von den Features in ASP.net Web Forms für das Binden von Daten aus Datenquellen an UI-Steuerelemente. Im Abschnitt [Umgang mit Daten](data.md) wird die Behandlung von Daten aus verschiedenen Datenquellen behandelt.

Verwenden Sie zum Erstellen einer bidirektionalen Datenbindung von einer Benutzeroberflächen Komponente zum Status der Komponente das `@bind` direktivenattribut. Im folgenden Beispiel ist der Wert des Kontrollkästchens an das- `isChecked` Feld gebunden.

```razor
<input type="checkbox" @bind="isChecked" />

@code {
    bool isChecked;
}
```

Wenn die Komponente gerendert wird, wird der Wert des Kontrollkästchens auf den Wert des Felds festgelegt `isChecked` . Wenn der Benutzer das Kontrollkästchen schaltet, wird das `onchange` -Ereignis ausgelöst, und das `isChecked` Feld wird auf den neuen Wert festgelegt. Die `@bind` Syntax in diesem Fall entspricht dem folgenden Markup:

```razor
<input value="@isChecked" @onchange="(UIChangeEventArgs e) => isChecked = e.Value" />
```

Verwenden Sie das-Attribut, um das für die Bindung verwendete Ereignis zu ändern `@bind:event` .

```razor
<input @bind="text" @bind:event="oninput" />
<p>@text</p>

@code {
    string text;
}
```

Komponenten können auch die Datenbindung an Ihre Parameter unterstützen. Definieren Sie für die Datenbindung einen Ereignis Rückruf Parameter mit dem gleichen Namen wie der bindbare Parameter. Das Suffix "Changed" wird dem Namen hinzugefügt.

*PasswordBox. Razor*

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

Wenn Sie eine Datenbindung an ein zugrunde liegendes UI-Element verketten möchten, legen Sie den Wert fest, und behandeln Sie das Ereignis direkt für das UI-Element, statt das- `@bind` Attribut

Verwenden Sie zum Binden an einen Komponenten Parameter ein- `@bind-{Parameter}` Attribut, um den Parameter anzugeben, an den die Bindung erfolgen soll.

```razor
<PasswordBox @bind-Password="password" />

@code {
    string password;
}
```

## <a name="state-changes"></a>Statusänderungen

Wenn sich der Zustand der Komponente außerhalb eines normalen UI-Ereignisses oder Ereignis Rückrufs geändert hat, muss die Komponente manuell signalisieren, dass Sie erneut gerendert werden muss. Um zu signalisieren, dass sich der Status einer Komponente geändert hat, müssen Sie die- `StateHasChanged` Methode für die Komponente aufzurufen.

Im folgenden Beispiel zeigt eine Komponente eine Nachricht von einem Dienst an `AppState` , der von anderen Teilen der APP aktualisiert werden kann. Die Komponente registriert die- `StateHasChanged` Methode mit dem- `AppState.OnChange` Ereignis, sodass die Komponente immer dann gerendert wird, wenn die Nachricht aktualisiert wird.

```csharp
public class AppState
{
    public string Message { get; }

    // Lets components receive change notifications
    public event Action OnChange;

    public void UpdateMessage(string message)
    {
        Message = message;
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

## <a name="component-lifecycle"></a>Komponenten Lebenszyklus

Das ASP.net Web Forms Framework verfügt über klar definierte Lebenszyklus Methoden für Module, Seiten und Steuerelemente. Das folgende Steuerelement implementiert z. b. Ereignishandler für `Init` das `Load` -,-und- `UnLoad` Lebenszyklus Ereignis:

*Counter.ascx.cs*

```csharp
public partial class Counter : System.Web.UI.UserControl
{
    protected void Page_Init(object sender, EventArgs e) { ... }
    protected void Page_Load(object sender, EventArgs e) { ... }
    protected void Page_UnLoad(object sender, EventArgs e) { ... }
}
```

Blazor-Komponenten verfügen auch über einen klar definierten Lebenszyklus. Der Lebenszyklus einer Komponente kann verwendet werden, um den Komponenten Status zu initialisieren und erweiterte Komponenten Verhalten zu implementieren.

Alle Komponenten Lebenszyklus-Methoden von blazor haben sowohl synchrone als auch asynchrone Versionen. Das Komponenten Rendering ist synchron. Asynchrone Logik kann nicht als Teil des Komponenten Rendering ausgeführt werden. Alle asynchronen Logik muss als Teil einer `async` Lebenszyklus Methode ausgeführt werden.

### <a name="oninitialized"></a>Oninitialisiert

Die `OnInitialized` -und- `OnInitializedAsync` Methoden werden verwendet, um die Komponente zu initialisieren. Eine Komponente wird in der Regel initialisiert, nachdem Sie erstmals gerendert wurde. Nachdem eine Komponente initialisiert wurde, kann Sie mehrmals gerendert werden, bevor Sie schließlich verworfen wird. Die `OnInitialized` -Methode ähnelt dem `Page_Load` -Ereignis in ASP.net Web Forms Seiten und Steuerelemente.

```csharp
protected override void OnInitialized() { ... }
protected override async Task OnInitializedAsync() { await ... }
```

### <a name="onparametersset"></a>Onparametersset

Die `OnParametersSet` -Methode und die- `OnParametersSetAsync` Methode werden aufgerufen, wenn eine Komponente Parameter von ihrem übergeordneten Element erhalten hat und der Wert Eigenschaften zugewiesen werden. Diese Methoden werden nach der Initialisierung der Komponente und *jedes Mal, wenn die Komponente gerendert wird*, ausgeführt.

```csharp
protected override void OnParametersSet() { ... }
protected override async Task OnParametersSetAsync() { await ... }
```

### <a name="onafterrender"></a>Onafterrendering

Die `OnAfterRender` -Methode und die- `OnAfterRenderAsync` Methode werden aufgerufen, nachdem eine Komponente das Rendering abgeschlossen hat. Element-und Komponenten Verweise werden an diesem Punkt aufgefüllt (Weitere Informationen zu diesen Konzepten finden Sie unten). Die Interaktivität mit dem Browser ist an diesem Punkt aktiviert. Interaktionen mit der Dom-und JavaScript-Ausführung können problemlos erfolgen.

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

`OnAfterRender`und werden `OnAfterRenderAsync` *nicht aufgerufen, wenn Sie auf dem Server vorab verwendet*werden.

Der- `firstRender` Parameter ist `true` das erste Mal, wenn die Komponente gerendert wird, andernfalls ist der Wert `false` .

### <a name="idisposable"></a>IDisposable

Blazor-Komponenten können implementieren `IDisposable` , um Ressourcen freizugeben, wenn die Komponente aus der Benutzeroberfläche entfernt wird. Eine Razor-Komponente kann `IDispose` mithilfe der- `@implements` Direktive implementiert werden:

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

## <a name="capture-component-references"></a>Komponenten Verweise erfassen

In ASP.net Web Forms ist es üblich, eine Steuerelement Instanz direkt im Code zu bearbeiten, indem Sie sich auf Ihre ID bezieht. In blazor ist es auch möglich, einen Verweis auf eine Komponente zu erfassen und zu bearbeiten, obwohl Sie viel weniger häufig ist.

Um einen Komponenten Verweis in blazor zu erfassen, verwenden Sie das `@ref` direktivenattribut. Der Wert des-Attributs sollte mit dem Namen eines festleg baren Felds mit dem gleichen Typ wie die Komponente übereinstimmen, auf die verwiesen wird.

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

Wenn die übergeordnete Komponente gerendert wird, wird das Feld mit der untergeordneten Komponenteninstanz aufgefüllt. Anschließend können Sie Methoden für die Komponenteninstanz auf oder anderweitig bearbeiten.

Das direkte Bearbeiten des Komponenten Zustands mithilfe von Komponenten verweisen ist nicht empfehlenswert. Dadurch wird verhindert, dass die Komponente automatisch zu den richtigen Zeitpunkten gerendert wird.

## <a name="capture-element-references"></a>Element Verweise erfassen

Blazor-Komponenten können Verweise auf ein Element erfassen. Im Gegensatz zu HTML-Server Steuerelementen in ASP.net-Web Forms können Sie das DOM nicht direkt mithilfe eines Element Verweises in blazor manipulieren. Blazor verarbeitet die meisten Dom-Interaktionen für Sie mithilfe des DOM-diffingalgorithmus. Erfasste Element Verweise in blazor sind nicht transparent. Sie werden jedoch verwendet, um einen bestimmten Element Verweis in einem JavaScript-Interop-Befehl zu übergeben. Weitere Informationen zum JavaScript-Interop finden Sie unter [ASP.net Core blazor JavaScript-Interop](/aspnet/core/blazor/javascript-interop).

## <a name="templated-components"></a>Komponenten mit Vorlagen

In ASP.net Web Forms können Sie Steuer *Elemente*mit Vorlagen erstellen. Mithilfe von Vorlagen basierten Steuerelementen kann der Entwickler einen Teil des HTML-Code angeben, der zum Rendering eines Container Steuer Elements verwendet wird. Die Mechanismen der Erstellung von Vorlagen basierten Server Steuerelementen sind komplex, aber Sie ermöglichen leistungsstarke Szenarios zum Rendern von Daten auf Benutzer anpassbare Weise. Beispiele für Steuerelemente mit Vorlagen sind `Repeater` und `DataList` .

Blazor-Komponenten können auch durch Definieren von Komponenten Parametern vom Typ oder Vorlagen Weise durch definiert werden `RenderFragment` `RenderFragment<T>` . Ein `RenderFragment` stellt einen Block von Razor-Markup dar, der dann von der Komponente gerendert werden kann. Ein `RenderFragment<T>` ist ein Block von Razor-Markup, das einen Parameter annimmt, der beim Rendern des renderfragments angegeben werden kann.

### <a name="child-content"></a>Untergeordneter Inhalt

Blazor-Komponenten können ihren untergeordneten Inhalt als einen erfassen `RenderFragment` und diesen Inhalt als Teil des Komponenten Rendering rendern. Zum Erfassen von untergeordnetem Inhalt definieren Sie einen Komponenten Parameter vom Typ, `RenderFragment` und benennen Sie ihn `ChildContent` .

*Childcontentcomponent. Razor*

```razor
<h1>Component with child content</h1>

<div>@ChildContent</div>

@code {
    [Parameter]
    public RenderFragment ChildContent { get; set; }
}
```

Eine übergeordnete Komponente kann dann untergeordneten Inhalt mithilfe von normalem Razor-Syntax bereitstellen.

```razor
<ChildContentComponent>
    <p>The time is @DateTime.Now</p>
</ChildContentComponent>
```

### <a name="template-parameters"></a>Vorlagenparameter

Eine vorlagenbasierte blazor-Komponente kann auch mehrere Komponenten Parameter vom Typ `RenderFragment` oder definieren `RenderFragment<T>` . Der-Parameter für einen `RenderFragment<T>` kann angegeben werden, wenn er aufgerufen wird. Um einen generischen Typparameter für eine Komponente anzugeben, verwenden Sie die `@typeparam` Razor-Direktive.

*Simplelistview. Razor*

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

Wenn Sie eine auf Vorlagen basierende Komponente verwenden, können die Vorlagen Parameter mit untergeordneten Elementen angegeben werden, die den Namen der Parameter entsprechen. Komponenten Argumente vom Typ, `RenderFragment<T>` die als-Elemente übergeben werden, haben einen impliziten Parameter mit dem Namen `context` Sie können den Namen dieses implementierenden Parameters mithilfe des- `Context` Attributs für das untergeordnete-Element ändern. Alle generischen Typparameter können mithilfe eines Attributs angegeben werden, das mit dem Namen des Typparameters übereinstimmt. Der Typparameter wird nach Möglichkeit abgeleitet:

```razor
<SimpleListView Items="messages" TItem="string">
    <Heading>
        <h1>My list</h1>
    </Heading>
    <ItemTemplate Context="message">
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

Eine blazor-Komponente wird in der Regel in einer einzelnen *Razor* -Datei erstellt. Es ist jedoch auch möglich, den Code und das Markup mithilfe einer Code Behind-Datei zu trennen. Um eine Komponenten Datei zu verwenden, fügen Sie eine c#-Datei hinzu, die mit dem Dateinamen der Komponenten Datei übereinstimmt, jedoch mit einer hinzugefügten Erweiterung *. cs* (*counter.Razor.cs*). Verwenden Sie die c#-Datei, um eine Basisklasse für die Komponente zu definieren. Sie können der Basisklasse einen beliebigen Namen benennen, aber es ist üblich, die Klasse mit der Komponenten Klasse zu benennen, aber mit einer `Base` Erweiterung hinzugefügt ( `CounterBase` ). Die komponentenbasierte Klasse muss auch von abgeleitet werden `ComponentBase` . Fügen Sie dann in der Razor-Komponenten Datei die- `@inherits` Direktive hinzu, um die Basisklasse für die Komponente ( `@inherits CounterBase` ) anzugeben.

*Counter. Razor*

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

Die Sichtbarkeit der Komponenten Elemente in der Basisklasse muss oder sein, um `protected` `public` für die Komponenten Klasse sichtbar zu sein.

## <a name="additional-resources"></a>Zusätzliche Ressourcen

Das vorherige ist keine umfassende Behandlung aller Aspekte von blazor-Komponenten. Weitere Informationen zum [Erstellen und Verwenden von ASP.net Core Razor-Komponenten](/aspnet/core/blazor/components)finden Sie in der blazor-Dokumentation.

>[!div class="step-by-step"]
>[Zurück](app-startup.md)
>[Weiter](pages-routing-layouts.md)
