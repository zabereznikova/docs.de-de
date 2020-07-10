---
title: Seiten, Routing und Layouts
description: Erfahren Sie, wie Sie Seiten in Erstellen Blazor , mit dem Client seitigen Routing arbeiten und Seitenlayouts verwalten.
author: danroth27
ms.author: daroth
no-loc:
- Blazor
ms.date: 09/19/2019
ms.openlocfilehash: fc1f6f9420c7149b6e67123f2f68bef75667aa0c
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/09/2020
ms.locfileid: "86173106"
---
# <a name="pages-routing-and-layouts"></a>Seiten, Routing und Layouts

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

ASP.net Web Forms-apps bestehen aus Seiten, die in *aspx* -Dateien definiert sind. Die Adresse jeder Seite basiert auf dem physischen Dateipfad im Projekt. Wenn ein Browser eine Anforderung an die Seite sendet, wird der Inhalt der Seite auf dem Server dynamisch gerendert. Die renderingkonten sowohl für das HTML-Markup der Seite als auch für die zugehörigen Server Steuerelemente.

In Blazor ist jede Seite in der App eine Komponente, die in der Regel in *einer Razor* -Datei mit einer oder mehreren angegebenen Routen definiert ist. Das Routing erfolgt größtenteils auf Clientseite, ohne eine bestimmte Server Anforderung einzubeziehen. Der Browser sendet zuerst eine Anforderung an die Stamm Adresse der app. Eine Stamm `Router` Komponente in der Blazor App behandelt dann abfangen-Navigationsanforderungen und Sie an die richtige Komponente.

Blazorunterstützt auch *Deep Linking*. Eine Deep-Verknüpfung tritt auf, wenn der Browser eine Anforderung an eine bestimmte Route sendet, die nicht der Stamm der APP ist. Anforderungen für Deep-Links, die an den Server gesendet werden, werden an die APP weitergeleitet Blazor , die dann die Client seitige Clientseite an die richtige Komponente weiterleitet.

Eine einfache Seite in ASP.net-Web Forms kann das folgende Markup enthalten:

*Name. aspx*

```aspx-csharp
<%@ Page Title="Name" Language="C#" MasterPageFile="~/Site.Master" AutoEventWireup="true" CodeBehind="Name.aspx.cs" Inherits="WebApplication1.Name" %>

<asp:Content ID="BodyContent" ContentPlaceHolderID="MainContent" runat="server">
    <div>
        What is your name?<br />
        <asp:TextBox ID="TextBox1" runat="server"></asp:TextBox>
        <asp:Button ID="Button1" runat="server" Text="Submit" OnClick="Button1_Click" />
    </div>
    <div>
        <asp:Literal ID="Literal1" runat="server" />
    </div>
</asp:Content>
```

*Name.aspx.cs*

```csharp
public partial class Name : System.Web.UI.Page
{
    protected void Button1_Click1(object sender, EventArgs e)
    {
        Literal1.Text = "Hello " + TextBox1.Text;
    }
}
```

Die entsprechende Seite in einer- Blazor App würde wie folgt aussehen:

*Name. Razor*

```razor
@page "/Name"
@layout MainLayout

<div>
    What is your name?<br />
    <input @bind="text" />
    <button @onclick="OnClick">Submit</button>
</div>
<div>
    @if (name != null)
    {
        @:Hello @name
    }
</div>

@code {
    string text;
    string name;

    void OnClick() {
        name = text;
    }
}
```

## <a name="create-pages"></a>Erstellen von Seiten

Um eine Seite in zu erstellen Blazor , erstellen Sie eine-Komponente und fügen die `@page` Razor-Direktive hinzu, um die Route für die Komponente anzugeben. Die- `@page` Direktive nimmt einen einzelnen Parameter, der der Komponente hinzugefügt werden soll, an.

```razor
@page "/counter"
```

Der Routen Vorlagen Parameter ist erforderlich. Im Gegensatz zu ASP.net Web Forms wird die Route zu einer Blazor Komponente nicht von Ihrem Datei Speicherort abgeleitet (obwohl dies möglicherweise eine in der Zukunft hinzugefügte Funktion *ist* ).

Die Syntax der Routen Vorlage ist die gleiche grundlegende Syntax, die für das Routing in ASP.net-Web Forms verwendet wird. Routen Parameter werden in der Vorlage mithilfe von geschweiften Klammern angegeben. Blazorbindet Routen Werte an Komponenten Parameter mit dem gleichen Namen (ohne Beachtung der Groß-/Kleinschreibung).

```razor
@page "/product/{id}"

<h1>Product @Id</h1>

@code {
    [Parameter]
    public string Id { get; set; }
}
```

Sie können auch Einschränkungen für den Wert des Routen Parameters angeben. Um z. b. die Produkt-ID auf zu beschränken, gilt Folgendes `int` :

```razor
@page "/product/{id:int}"

<h1>Product @Id</h1>

@code {
    [Parameter]
    public int Id { get; set; }
}
```

Eine vollständige Liste der von unterstützten Routen Einschränkungen Blazor finden Sie unter [Routen Einschränkungen](/aspnet/core/blazor/routing#route-constraints).

## <a name="router-component"></a>Routerkomponente

Das Routing in Blazor wird von der- `Router` Komponente behandelt. Die `Router` Komponente wird in der Regel in der Stamm Komponente der APP (*app. Razor*) verwendet.

```razor
<Router AppAssembly="@typeof(Program).Assembly">
    <Found Context="routeData">
        <RouteView RouteData="@routeData" DefaultLayout="@typeof(MainLayout)" />
    </Found>
    <NotFound>
        <LayoutView Layout="@typeof(MainLayout)">
            <p>Sorry, there's nothing at this address.</p>
        </LayoutView>
    </NotFound>
</Router>
```

Die `Router` Komponente ermittelt die Routing fähigen Komponenten im angegebenen `AppAssembly` und im optional angegebenen `AdditionalAssemblies` . Wenn der Browser navigiert, `Router` fängt die Navigation ab und rendert den Inhalt des- `Found` Parameters mit dem extrahierten `RouteData` , wenn eine Route mit der Adresse übereinstimmt, andernfalls `Router` rendert den- `NotFound` Parameter.

Die `RouteView` Komponente übernimmt das Rendern der übereinstimmenden, von angegebenen Komponente `RouteData` mit dem zugehörigen Layout, wenn Sie über eine verfügt. Wenn die übereinstimmende Komponente kein Layout hat, wird der optional angegebene `DefaultLayout` verwendet.

Die `LayoutView` Komponente rendert ihren untergeordneten Inhalt innerhalb des angegebenen Layouts. Im weiteren Verlauf dieses Kapitels betrachten wir die Layouts ausführlicher.

## <a name="navigation"></a>Navigation

In ASP.net Web Forms wird die Navigation zu einer anderen Seite durch Zurückgeben einer Umleitungs Antwort an den Browser auslöst. Beispiel:

```csharp
protected void NavigateButton_Click(object sender, EventArgs e)
{
    Response.Redirect("Counter");
}
```

Das Zurückgeben einer Umleitungs Antwort ist in der Regel nicht möglich Blazor . Blazorverwendet kein Anforderungs-Antwort-Modell. Sie können Browser Navigation jedoch direkt wie bei JavaScript auslassen.

Blazorstellt einen `NavigationManager` Dienst bereit, der für folgende Aktionen verwendet werden kann:

- Aktuelle Browser Adresse erhalten
- Basisadresse erhalten
- Navigations Navigation
- Benachrichtigen, wenn sich die Adresse ändert

Verwenden Sie die-Methode, um zu einer anderen Adresse zu navigieren `NavigateTo` :

```razor
@page "/"
@inject NavigationManager NavigationManager

<button @onclick="Navigate">Navigate</button>

@code {
    void Navigate() {
        NavigationManager.NavigateTo("counter");
    }
}
```

Eine Beschreibung aller Member `NavigationManager` finden Sie unter [URI-und Navigations Zustands Hilfen](/aspnet/core/blazor/routing#uri-and-navigation-state-helpers).

## <a name="base-urls"></a>Basis-URLs

Wenn Ihre Blazor app unter einem Basispfad bereitgestellt wird, müssen Sie die Basis-URL in den Seiten Metadaten mithilfe des `<base>` Tags für die Routing to work-Eigenschaft angeben. Wenn die Hostseite für die App mithilfe von Razor Server gerendert wird, können Sie die `~/` -Syntax verwenden, um die Basisadresse der APP anzugeben. Wenn die Hostseite statischer HTML-Code ist, müssen Sie die Basis-URL explizit angeben.

```html
<base href="~/" />
```

## <a name="page-layout"></a>Seitenlayout

Das Seitenlayout in ASP.net-Web Forms wird von Master Seiten behandelt. Master Seiten definieren eine Vorlage mit einem oder mehreren Inhalts Platzhaltern, die dann von einzelnen Seiten bereitgestellt werden können. Masterseiten werden in *Master* Dateien definiert und beginnen mit der- `<%@ Master %>` Direktive. Der Inhalt der *Master* Dateien ist so codiert wie eine *aspx* -Seite, mit dem Hinzufügen von Steuer `<asp:ContentPlaceHolder>` Elementen, um zu markieren, wo Seiteninhalte bereitstellen können.

*Site.master*

```aspx-csharp
<%@ Master Language="C#" AutoEventWireup="true" CodeBehind="Site.master.cs" Inherits="WebApplication1.SiteMaster" %>

<!DOCTYPE html>
<html lang="en">
<head runat="server">
    <meta charset="utf-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title><%: Page.Title %> - My ASP.NET Application</title>
    <link href="~/favicon.ico" rel="shortcut icon" type="image/x-icon" />
</head>
<body>
    <form runat="server">
        <div class="container body-content">
            <asp:ContentPlaceHolder ID="MainContent" runat="server">
            </asp:ContentPlaceHolder>
            <hr />
            <footer>
                <p>&copy; <%: DateTime.Now.Year %> - My ASP.NET Application</p>
            </footer>
        </div>
    </form>
</body>
</html>
```

In Blazor wird das Seitenlayout mithilfe von Layoutkomponenten behandelt. Layoutkomponenten erben von `LayoutComponentBase` , das eine einzelne `Body` Eigenschaft des Typs definiert `RenderFragment` , die zum Rendering der Inhalte der Seite verwendet werden kann.

*MainLayout. Razor*

```razor
@inherits LayoutComponentBase
<h1>Main layout</h1>
<div>
    @Body
</div>
```

Wenn die Seite mit einem Layout gerendert wird, wird die Seite im Inhalt des angegebenen Layouts an der Position gerendert, an der das Layout die-Eigenschaft rendert `Body` .

Verwenden Sie die-Direktive, um ein Layout auf eine Seite anzuwenden `@layout` :

```razor
@layout MainLayout
```

Sie können das Layout für alle Komponenten in einem Ordner und in Unterordnern mithilfe einer *_Imports Razor* -Datei angeben. Sie können auch ein Standardlayout für alle Seiten mithilfe der [Routerkomponente](#router-component)angeben.

Master Seiten können mehrere Inhalts Platzhalter definieren, aber Layouts in Blazor verfügen nur über eine einzige `Body` Eigenschaft. Diese Einschränkung der Blazor Layoutkomponenten wird in einer zukünftigen Version hoffentlich behoben werden.

Master Seiten in ASP.net-Web Forms können eingebettet werden. Das heißt, eine Master Seite kann auch eine Master Seite verwenden. Layoutkomponenten in Blazor werden möglicherweise ebenfalls eingefügt. Sie können eine Layoutkomponente auf eine Layoutkomponente anwenden. Der Inhalt des inneren Layouts wird innerhalb des äußeren Layouts gerendert.

*Childlayout. Razor*

```razor
@layout MainLayout
<h2>Child layout</h2>
<div>
    @Body
</div>
```

*Index. Razor*

```razor
@page "/"
@layout ChildLayout
<p>I'm in a nested layout!</p>
```

Die gerenderte Ausgabe für die Seite würde dann wie folgt lauten:

```html
<h1>Main layout</h1>
<div>
    <h2>Child layout</h2>
    <div>
        <p>I'm in a nested layout!</p>
    </div>
</div>
```

Layouts in Blazor definieren in der Regel nicht die Stamm-HTML-Elemente für eine Seite ( `<html>` , `<body>` , `<head>` usw.). Die Stamm-HTML-Elemente werden stattdessen auf Blazor der Hostseite einer APP definiert, die zum Rendering der anfänglichen HTML-Inhalte für die APP verwendet wird (siehe [Bootstrap Blazor ](project-structure.md#bootstrap-blazor)). Die Hostseite kann mehrere Stamm Komponenten für die APP mit umgebenden Markup Rendering darstellen.

Komponenten in Blazor , einschließlich Seiten, können keine `<script>` Tags darstellen. Diese renderingeinschränkung ist vorhanden, da `<script>` Tags einmal geladen werden und dann nicht geändert werden können. Unerwartetes Verhalten kann auftreten, wenn Sie versuchen, die Tags mithilfe Razor-Syntax dynamisch zu rendern. Stattdessen sollten alle `<script>` Tags der Host Seite der app hinzugefügt werden.

>[!div class="step-by-step"]
>[Zurück](components.md)
>[Weiter](state-management.md)
