---
title: Erstellen wiederverwendbarer Benutzeroberflächen Komponenten mitBlazor
description: Erfahren Sie, wie Sie wiederverwendbare UI-Komponenten mit erstellen Blazor und wie Sie mit ASP.net-Web Forms Steuerelementen vergleichen.
author: danroth27
ms.author: daroth
no-loc:
- Blazor
ms.date: 09/18/2019
ms.openlocfilehash: 9577fc916bb11783b885b2641242820865c0b115
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/09/2020
ms.locfileid: "86173339"
---
# <a name="build-reusable-ui-components-with-blazor"></a><span data-ttu-id="2cc97-103">Erstellen wiederverwendbarer Benutzeroberflächen Komponenten mitBlazor</span><span class="sxs-lookup"><span data-stu-id="2cc97-103">Build reusable UI components with Blazor</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="2cc97-104">Eine der schönen Aspekte von ASP.net Web Forms ist, wie Sie wiederverwendbare Elemente von Benutzeroberflächen Code in wiederverwendbare UI-Steuerelemente einkapseln kann.</span><span class="sxs-lookup"><span data-stu-id="2cc97-104">One of the beautiful things about ASP.NET Web Forms is how it enables encapsulation of reusable pieces of user interface (UI) code into reusable UI controls.</span></span> <span data-ttu-id="2cc97-105">Benutzerdefinierte Benutzer Steuerelemente können mithilfe von *ASCX* -Dateien im Markup definiert werden.</span><span class="sxs-lookup"><span data-stu-id="2cc97-105">Custom user controls can be defined in markup using *.ascx* files.</span></span> <span data-ttu-id="2cc97-106">Mit vollständiger Designer Unterstützung können Sie auch aufwändige Server Steuerelemente im Code erstellen.</span><span class="sxs-lookup"><span data-stu-id="2cc97-106">You can also build elaborate server controls in code with full designer support.</span></span>

Blazor<span data-ttu-id="2cc97-107">unterstützt auch die Benutzeroberflächen Kapselung durch *Komponenten*.</span><span class="sxs-lookup"><span data-stu-id="2cc97-107"> also supports UI encapsulation through *components*.</span></span> <span data-ttu-id="2cc97-108">Eine Komponente:</span><span class="sxs-lookup"><span data-stu-id="2cc97-108">A component:</span></span>

- <span data-ttu-id="2cc97-109">Bei handelt es sich um einen eigenständigen Block von Benutzeroberflächen.</span><span class="sxs-lookup"><span data-stu-id="2cc97-109">Is a self-contained chunk of UI.</span></span>
- <span data-ttu-id="2cc97-110">Behält seine eigene Zustands-und Renderinglogik bei.</span><span class="sxs-lookup"><span data-stu-id="2cc97-110">Maintains its own state and rendering logic.</span></span>
- <span data-ttu-id="2cc97-111">Kann Benutzeroberflächen-Ereignishandler definieren, an Eingabedaten binden und ihren eigenen Lebenszyklus verwalten.</span><span class="sxs-lookup"><span data-stu-id="2cc97-111">Can define UI event handlers, bind to input data, and manage its own lifecycle.</span></span>
- <span data-ttu-id="2cc97-112">Wird in der Regel in einer *Razor* -Datei mit Razor-Syntax definiert.</span><span class="sxs-lookup"><span data-stu-id="2cc97-112">Is typically defined in a *.razor* file using Razor syntax.</span></span>

## <a name="an-introduction-to-razor"></a><span data-ttu-id="2cc97-113">Eine Einführung in Razor</span><span class="sxs-lookup"><span data-stu-id="2cc97-113">An introduction to Razor</span></span>

<span data-ttu-id="2cc97-114">Razor ist eine einfache Markup Vorlagen Sprache, die auf HTML und c# basiert.</span><span class="sxs-lookup"><span data-stu-id="2cc97-114">Razor is a light-weight markup templating language based on HTML and C#.</span></span> <span data-ttu-id="2cc97-115">Mit Razor können Sie nahtlos zwischen Markup und c#-Code wechseln, um die Komponenten Rendering-Logik zu definieren.</span><span class="sxs-lookup"><span data-stu-id="2cc97-115">With Razor, you can seamlessly transition between markup and C# code to define your component rendering logic.</span></span> <span data-ttu-id="2cc97-116">Wenn die *Razor* -Datei kompiliert wird, wird die Renderinglogik auf strukturierte Weise in einer .NET-Klasse aufgezeichnet.</span><span class="sxs-lookup"><span data-stu-id="2cc97-116">When the *.razor* file is compiled, the rendering logic is captured in a structured way in a .NET class.</span></span> <span data-ttu-id="2cc97-117">Der Name der kompilierten Klasse stammt aus dem Namen der *Razor* -Datei.</span><span class="sxs-lookup"><span data-stu-id="2cc97-117">The name of the compiled class is taken from the *.razor* file name.</span></span> <span data-ttu-id="2cc97-118">Der Namespace wird aus dem Standard Namespace für das Projekt und den Ordner Pfad entnommen, oder Sie können den Namespace mithilfe der-Anweisung explizit angeben `@namespace` (Weitere Informationen zu Razor-Direktiven finden Sie unten).</span><span class="sxs-lookup"><span data-stu-id="2cc97-118">The namespace is taken from the default namespace for the project and the folder path, or you can explicitly specify the namespace using the `@namespace` directive (more on Razor directives below).</span></span>

<span data-ttu-id="2cc97-119">Die Renderinglogik einer Komponente wird mithilfe von normalem HTML-Markup mit dynamischer Logik erstellt, die mit c# hinzugefügt wurde.</span><span class="sxs-lookup"><span data-stu-id="2cc97-119">A component's rendering logic is authored using normal HTML markup with dynamic logic added using C#.</span></span> <span data-ttu-id="2cc97-120">Das `@` Zeichen wird für den Übergang zu c# verwendet.</span><span class="sxs-lookup"><span data-stu-id="2cc97-120">The `@` character is used to transition to C#.</span></span> <span data-ttu-id="2cc97-121">Razor ist in der Regel intelligent, wenn Sie zu HTML zurück gewechselt haben.</span><span class="sxs-lookup"><span data-stu-id="2cc97-121">Razor is typically smart about figuring out when you've switched back to HTML.</span></span> <span data-ttu-id="2cc97-122">Die folgende Komponente rendert z. b. ein `<p>` Tag mit der aktuellen Uhrzeit:</span><span class="sxs-lookup"><span data-stu-id="2cc97-122">For example, the following component renders a `<p>` tag with the current time:</span></span>

```razor
<p>@DateTime.Now</p>
```

<span data-ttu-id="2cc97-123">Um den Anfang und das Beenden eines c#-Ausdrucks explizit anzugeben, verwenden Sie Klammern:</span><span class="sxs-lookup"><span data-stu-id="2cc97-123">To explicitly specify the beginning and ending of a C# expression, use parentheses:</span></span>

```razor
<p>@(DateTime.Now)</p>
```

<span data-ttu-id="2cc97-124">Razor erleichtert auch die Verwendung der c#-Ablauf Steuerung in ihrer Renderinglogik.</span><span class="sxs-lookup"><span data-stu-id="2cc97-124">Razor also makes it easy to use C# control flow in your rendering logic.</span></span> <span data-ttu-id="2cc97-125">Beispielsweise können Sie einige HTML-Code wie folgt bedingt darstellen:</span><span class="sxs-lookup"><span data-stu-id="2cc97-125">For example, you can conditionally render some HTML like this:</span></span>

```razor
@if (value % 2 == 0)
{
    <p>The value was even.</p>
}
```

<span data-ttu-id="2cc97-126">Sie können auch eine Liste von Elementen generieren, indem Sie eine normale c#-Schleife wie die folgende verwenden `foreach` :</span><span class="sxs-lookup"><span data-stu-id="2cc97-126">Or you can generate a list of items using a normal C# `foreach` loop like this:</span></span>

```razor
<ul>
@foreach (var item in items)
{
    <li>@item.Text</li>
}
</ul>
```

<span data-ttu-id="2cc97-127">Razor-Direktiven, wie Direktiven in ASP.net-Web Forms, Steuern viele Aspekte der Kompilierung einer Razor-Komponente.</span><span class="sxs-lookup"><span data-stu-id="2cc97-127">Razor directives, like directives in ASP.NET Web Forms, control many aspects of how a Razor component is compiled.</span></span> <span data-ttu-id="2cc97-128">Beispiele hierfür sind:</span><span class="sxs-lookup"><span data-stu-id="2cc97-128">Examples include the component's:</span></span>

- <span data-ttu-id="2cc97-129">Namespace</span><span class="sxs-lookup"><span data-stu-id="2cc97-129">Namespace</span></span>
- <span data-ttu-id="2cc97-130">Basisklasse</span><span class="sxs-lookup"><span data-stu-id="2cc97-130">Base class</span></span>
- <span data-ttu-id="2cc97-131">Implementierte Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="2cc97-131">Implemented interfaces</span></span>
- <span data-ttu-id="2cc97-132">Generische Parameter</span><span class="sxs-lookup"><span data-stu-id="2cc97-132">Generic parameters</span></span>
- <span data-ttu-id="2cc97-133">Importierte Namespaces</span><span class="sxs-lookup"><span data-stu-id="2cc97-133">Imported namespaces</span></span>
- <span data-ttu-id="2cc97-134">Routen</span><span class="sxs-lookup"><span data-stu-id="2cc97-134">Routes</span></span>

<span data-ttu-id="2cc97-135">Razor-Direktiven beginnen mit dem `@` Zeichen und werden in der Regel am Anfang einer neuen Zeile am Anfang der Datei verwendet.</span><span class="sxs-lookup"><span data-stu-id="2cc97-135">Razor directives start with the `@` character and are typically used at the start of a new line at the start of the file.</span></span> <span data-ttu-id="2cc97-136">Die `@namespace` -Direktive definiert z. b. den-Namespace der Komponente:</span><span class="sxs-lookup"><span data-stu-id="2cc97-136">For example, the `@namespace` directive defines the component's namespace:</span></span>

```razor
@namespace MyComponentNamespace
```

<span data-ttu-id="2cc97-137">In der folgenden Tabelle werden die verschiedenen Razor-Direktiven, die in verwendet werden Blazor , sowie deren Web Forms ASP.NET-Entsprechungen zusammengefasst, sofern vorhanden</span><span class="sxs-lookup"><span data-stu-id="2cc97-137">The following table summarizes the various Razor directives used in Blazor and their ASP.NET Web Forms equivalents, if they exist.</span></span>

|<span data-ttu-id="2cc97-138">Anweisung</span><span class="sxs-lookup"><span data-stu-id="2cc97-138">Directive</span></span>    |<span data-ttu-id="2cc97-139">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2cc97-139">Description</span></span>|<span data-ttu-id="2cc97-140">Beispiel</span><span class="sxs-lookup"><span data-stu-id="2cc97-140">Example</span></span>|<span data-ttu-id="2cc97-141">Web Forms Äquivalent</span><span class="sxs-lookup"><span data-stu-id="2cc97-141">Web Forms equivalent</span></span>|
|-------------|-----------|-------|--------------------|
|`@attribute` |<span data-ttu-id="2cc97-142">Fügt der Komponente ein Attribut auf Klassenebene hinzu.</span><span class="sxs-lookup"><span data-stu-id="2cc97-142">Adds a class-level attribute to the component</span></span>|`@attribute [Authorize]`|<span data-ttu-id="2cc97-143">Keine</span><span class="sxs-lookup"><span data-stu-id="2cc97-143">None</span></span>|
|`@code`      |<span data-ttu-id="2cc97-144">Fügt der Komponente Klassenmember hinzu.</span><span class="sxs-lookup"><span data-stu-id="2cc97-144">Adds class members to the component</span></span>|`@code { ... }`|`<script runat="server">...</script>`|
|`@implements`|<span data-ttu-id="2cc97-145">Implementiert die angegebene Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="2cc97-145">Implements the specified interface</span></span>|`@implements IDisposable`|<span data-ttu-id="2cc97-146">Verwenden des CodeBehinds</span><span class="sxs-lookup"><span data-stu-id="2cc97-146">Use code-behind</span></span>|
|`@inherits`  |<span data-ttu-id="2cc97-147">Erbt von der angegebenen Basisklasse</span><span class="sxs-lookup"><span data-stu-id="2cc97-147">Inherits from the specified base class</span></span>|`@inherits MyComponentBase`|`<%@ Control Inherits="MyUserControlBase" %>`|
|`@inject`    |<span data-ttu-id="2cc97-148">Fügt einen Dienst in die Komponente ein.</span><span class="sxs-lookup"><span data-stu-id="2cc97-148">Injects a service into the component</span></span>|`@inject IJSRuntime JS`|<span data-ttu-id="2cc97-149">Keine</span><span class="sxs-lookup"><span data-stu-id="2cc97-149">None</span></span>|
|`@layout`    |<span data-ttu-id="2cc97-150">Gibt eine Layoutkomponente für die Komponente an.</span><span class="sxs-lookup"><span data-stu-id="2cc97-150">Specifies a layout component for the component</span></span>|`@layout MainLayout`|`<%@ Page MasterPageFile="~/Site.Master" %>`|
|`@namespace` |<span data-ttu-id="2cc97-151">Legt den Namespace für die Komponente fest.</span><span class="sxs-lookup"><span data-stu-id="2cc97-151">Sets the namespace for the component</span></span>|`@namespace MyNamespace`|<span data-ttu-id="2cc97-152">Keine</span><span class="sxs-lookup"><span data-stu-id="2cc97-152">None</span></span>|
|`@page`      |<span data-ttu-id="2cc97-153">Gibt die Route für die Komponente an.</span><span class="sxs-lookup"><span data-stu-id="2cc97-153">Specifies the route for the component</span></span>|`@page "/product/{id}"`|`<%@ Page %>`|
|`@typeparam` |<span data-ttu-id="2cc97-154">Gibt einen generischen Typparameter für die Komponente an.</span><span class="sxs-lookup"><span data-stu-id="2cc97-154">Specifies a generic type parameter for the component</span></span>|`@typeparam TItem`|<span data-ttu-id="2cc97-155">Verwenden des CodeBehinds</span><span class="sxs-lookup"><span data-stu-id="2cc97-155">Use code-behind</span></span>|
|`@using`     |<span data-ttu-id="2cc97-156">Gibt einen Namespace an, der in den Gültigkeitsbereich</span><span class="sxs-lookup"><span data-stu-id="2cc97-156">Specifies a namespace to bring into scope</span></span>|`@using MyComponentNamespace`|<span data-ttu-id="2cc97-157">Namespace in *web.config* hinzufügen</span><span class="sxs-lookup"><span data-stu-id="2cc97-157">Add namespace in *web.config*</span></span>|

<span data-ttu-id="2cc97-158">Razor-Komponenten machen außerdem eine umfassende Verwendung von *direktivenattributen* für Elemente, um verschiedene Aspekte der Kompilierung von Komponenten zu steuern (Ereignis Behandlung, Datenbindung, Verweise auf Komponenten & Elemente usw.).</span><span class="sxs-lookup"><span data-stu-id="2cc97-158">Razor components also make extensive use of *directive attributes* on elements to control various aspects of how components get compiled (event handling, data binding, component & element references, and so on).</span></span> <span data-ttu-id="2cc97-159">Direktivenattribute folgen allen allgemeinen generischen Syntax, bei der die Werte in Klammern optional sind:</span><span class="sxs-lookup"><span data-stu-id="2cc97-159">Directive attributes all follow a common generic syntax where the values in parenthesis are optional:</span></span>

```razor
@directive(-suffix(:name))(="value")
```

<span data-ttu-id="2cc97-160">In der folgenden Tabelle werden die verschiedenen Attribute der in verwendeten Razor-Direktiven zusammengefasst Blazor .</span><span class="sxs-lookup"><span data-stu-id="2cc97-160">The following table summarizes the various attributes for Razor directives used in Blazor.</span></span>

|<span data-ttu-id="2cc97-161">attribute</span><span class="sxs-lookup"><span data-stu-id="2cc97-161">Attribute</span></span>    |<span data-ttu-id="2cc97-162">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="2cc97-162">Description</span></span>|<span data-ttu-id="2cc97-163">Beispiel</span><span class="sxs-lookup"><span data-stu-id="2cc97-163">Example</span></span>|
|-------------|-----------|-------|
|`@attributes`|<span data-ttu-id="2cc97-164">Rendert ein Wörterbuch von Attributen.</span><span class="sxs-lookup"><span data-stu-id="2cc97-164">Renders a dictionary of attributes</span></span>|`<input @attributes="ExtraAttributes" />`|
|`@bind`      |<span data-ttu-id="2cc97-165">Erstellt eine bidirektionale Datenbindung.</span><span class="sxs-lookup"><span data-stu-id="2cc97-165">Creates a two-way data binding</span></span>    |`<input @bind="username" @bind:event="oninput" />`|
|`@on{event}` |<span data-ttu-id="2cc97-166">Fügt einen Ereignishandler für das angegebene Ereignis hinzu.</span><span class="sxs-lookup"><span data-stu-id="2cc97-166">Adds an event handler for the specified event</span></span>|`<button @onclick="IncrementCount">Click me!</button>`|
|`@key`       |<span data-ttu-id="2cc97-167">Gibt einen Schlüssel an, der vom diffingalgorithmus zum Beibehalten von Elementen in einer Auflistung verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="2cc97-167">Specifies a key to be used by the diffing algorithm for preserving elements in a collection</span></span>|`<DetailsEditor @key="person" Details="person.Details" />`|
|`@ref`       |<span data-ttu-id="2cc97-168">Zeichnet einen Verweis auf die Komponente oder das HTML-Element auf.</span><span class="sxs-lookup"><span data-stu-id="2cc97-168">Captures a reference to the component or HTML element</span></span>|`<MyDialog @ref="myDialog" />`|

<span data-ttu-id="2cc97-169">Die verschiedenen von verwendeten Direktivenattribute Blazor ( `@onclick` , `@bind` , `@ref` usw.) werden in den Abschnitten unten und in späteren Kapiteln behandelt.</span><span class="sxs-lookup"><span data-stu-id="2cc97-169">The various directive attributes used by Blazor (`@onclick`, `@bind`, `@ref`, and so on) are covered in the sections below and later chapters.</span></span>

<span data-ttu-id="2cc97-170">Viele der Syntaxen, die in *aspx* -und *ASCX* -Dateien verwendet werden, haben eine parallele Syntax in Razor.</span><span class="sxs-lookup"><span data-stu-id="2cc97-170">Many of the syntaxes used in *.aspx* and *.ascx* files have parallel syntaxes in Razor.</span></span> <span data-ttu-id="2cc97-171">Im folgenden finden Sie einen einfachen Vergleich der Syntaxen für ASP.net Web Forms und Razor.</span><span class="sxs-lookup"><span data-stu-id="2cc97-171">Below is a simple comparison of the syntaxes for ASP.NET Web Forms and Razor.</span></span>

|<span data-ttu-id="2cc97-172">Merkmal</span><span class="sxs-lookup"><span data-stu-id="2cc97-172">Feature</span></span>                      |<span data-ttu-id="2cc97-173">Web Forms</span><span class="sxs-lookup"><span data-stu-id="2cc97-173">Web Forms</span></span>           |<span data-ttu-id="2cc97-174">Syntax</span><span class="sxs-lookup"><span data-stu-id="2cc97-174">Syntax</span></span>               |<span data-ttu-id="2cc97-175">Razor</span><span class="sxs-lookup"><span data-stu-id="2cc97-175">Razor</span></span>         |<span data-ttu-id="2cc97-176">Syntax</span><span class="sxs-lookup"><span data-stu-id="2cc97-176">Syntax</span></span> |
|-----------------------------|--------------------|---------------------|--------------|-------|
|<span data-ttu-id="2cc97-177">Anweisungen</span><span class="sxs-lookup"><span data-stu-id="2cc97-177">Directives</span></span>                   |`<%@ [directive] %>`|`<%@ Page %>`        |`@[directive]`|`@page`|
|<span data-ttu-id="2cc97-178">Codeblöcke</span><span class="sxs-lookup"><span data-stu-id="2cc97-178">Code blocks</span></span>                  |`<% %>`             |`<% int x = 123; %>` |`@{ }`        |`@{ int x = 123; }`|
|<span data-ttu-id="2cc97-179">Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="2cc97-179">Expressions</span></span><br><span data-ttu-id="2cc97-180">(HTML-codiert)</span><span class="sxs-lookup"><span data-stu-id="2cc97-180">(HTML-encoded)</span></span>|`<%: %>`            |`<%:DateTime.Now %>` |<span data-ttu-id="2cc97-181">Verzerrungen`@`</span><span class="sxs-lookup"><span data-stu-id="2cc97-181">Implicit: `@`</span></span><br><span data-ttu-id="2cc97-182">Explizite`@()`</span><span class="sxs-lookup"><span data-stu-id="2cc97-182">Explicit: `@()`</span></span>|`@DateTime.Now`<br>`@(DateTime.Now)`|
|<span data-ttu-id="2cc97-183">Kommentare</span><span class="sxs-lookup"><span data-stu-id="2cc97-183">Comments</span></span>                     |`<%-- --%>`         |`<%-- Commented --%>`|`@* *@`       |`@* Commented *@`|
|<span data-ttu-id="2cc97-184">Datenbindung</span><span class="sxs-lookup"><span data-stu-id="2cc97-184">Data binding</span></span>                 |`<%# %>`            |`<%# Bind("Name") %>`|`@bind`       |`<input @bind="username" />`|

<span data-ttu-id="2cc97-185">Verwenden Sie die-Direktive, um der Razor-Komponenten Klasse Elemente hinzuzufügen `@code` .</span><span class="sxs-lookup"><span data-stu-id="2cc97-185">To add members to the Razor component class, use the `@code` directive.</span></span> <span data-ttu-id="2cc97-186">Dieses Verfahren ähnelt der Verwendung eines `<script runat="server">...</script>` Blocks in einem ASP.net-Web Forms Benutzer Steuerelement oder einer Seite.</span><span class="sxs-lookup"><span data-stu-id="2cc97-186">This technique is similar to using a `<script runat="server">...</script>` block in an ASP.NET Web Forms user control or page.</span></span>

```razor
@code {
    int count = 0;

    void IncrementCount()
    {
        count++;
    }
}
```

<span data-ttu-id="2cc97-187">Da Razor auf c# basiert, muss es in einem c#-Projekt (*. csproj*) kompiliert werden.</span><span class="sxs-lookup"><span data-stu-id="2cc97-187">Because Razor is based on C#, it must be compiled from within a C# project (*.csproj*).</span></span> <span data-ttu-id="2cc97-188">*Razor* -Dateien können nicht aus einem Visual Basic Projekt (*vbproj*) kompiliert werden.</span><span class="sxs-lookup"><span data-stu-id="2cc97-188">You can't compile *.razor* files from a Visual Basic project (*.vbproj*).</span></span> <span data-ttu-id="2cc97-189">Sie können weiterhin auf Visual Basic Projekte aus Ihrem Blazor Projekt verweisen.</span><span class="sxs-lookup"><span data-stu-id="2cc97-189">You can still reference Visual Basic projects from your Blazor project.</span></span> <span data-ttu-id="2cc97-190">Das Gegenteil gilt auch für.</span><span class="sxs-lookup"><span data-stu-id="2cc97-190">The opposite is true too.</span></span>

<span data-ttu-id="2cc97-191">Eine vollständige Razor-Syntax Referenz finden Sie unter [Razor-Syntax Referenz für ASP.net Core](/aspnet/core/mvc/views/razor).</span><span class="sxs-lookup"><span data-stu-id="2cc97-191">For a full Razor syntax reference, see [Razor syntax reference for ASP.NET Core](/aspnet/core/mvc/views/razor).</span></span>

## <a name="use-components"></a><span data-ttu-id="2cc97-192">Verwenden von Komponenten</span><span class="sxs-lookup"><span data-stu-id="2cc97-192">Use components</span></span>

<span data-ttu-id="2cc97-193">Abgesehen von normalem HTML können Komponenten auch andere Komponenten als Teil ihrer Renderinglogik verwenden.</span><span class="sxs-lookup"><span data-stu-id="2cc97-193">Aside from normal HTML, components can also use other components as part of their rendering logic.</span></span> <span data-ttu-id="2cc97-194">Die Syntax für die Verwendung einer Komponente in Razor ähnelt der Verwendung eines Benutzer Steuer Elements in einer ASP.net-Web Forms-app.</span><span class="sxs-lookup"><span data-stu-id="2cc97-194">The syntax for using a component in Razor is similar to using a user control in an ASP.NET Web Forms app.</span></span> <span data-ttu-id="2cc97-195">Komponenten werden mithilfe eines Elementtags angegeben, das mit dem Typnamen der Komponente übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="2cc97-195">Components are specified using an element tag that matches the type name of the component.</span></span> <span data-ttu-id="2cc97-196">Beispielsweise können Sie eine-Komponente wie die folgende hinzufügen `Counter` :</span><span class="sxs-lookup"><span data-stu-id="2cc97-196">For example, you can add a `Counter` component like this:</span></span>

```razor
<Counter />
```

<span data-ttu-id="2cc97-197">Im Gegensatz zu ASP.net-Web Forms Komponenten in Blazor :</span><span class="sxs-lookup"><span data-stu-id="2cc97-197">Unlike ASP.NET Web Forms, components in Blazor:</span></span>

- <span data-ttu-id="2cc97-198">Verwenden Sie kein Element Präfix (z `asp:` . b.).</span><span class="sxs-lookup"><span data-stu-id="2cc97-198">Don't use an element prefix (for example, `asp:`).</span></span>
- <span data-ttu-id="2cc97-199">Sie müssen nicht auf der Seite oder in der *web.config*registriert werden.</span><span class="sxs-lookup"><span data-stu-id="2cc97-199">Don't require registration on the page or in the *web.config*.</span></span>

<span data-ttu-id="2cc97-200">Stellen Sie sich die Razor-Komponenten wie .NET-Typen vor, denn das ist genau das, was Sie sind.</span><span class="sxs-lookup"><span data-stu-id="2cc97-200">Think of Razor components like you would .NET types, because that's exactly what they are.</span></span> <span data-ttu-id="2cc97-201">Wenn auf die Assembly verwiesen wird, die die Komponente enthält, kann die Komponente verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="2cc97-201">If the assembly containing the component is referenced, then the component is available for use.</span></span> <span data-ttu-id="2cc97-202">Um den Namespace der Komponente in den Gültigkeitsbereich zu bringen, wenden Sie die- `@using` Anweisung an</span><span class="sxs-lookup"><span data-stu-id="2cc97-202">To bring the component's namespace into scope, apply the `@using` directive:</span></span>

```razor
@using MyComponentLib

<Counter />
```

<span data-ttu-id="2cc97-203">Wie in den Standard Blazor Projekten zu sehen ist, werden `@using` Direktiven häufig in eine *_Imports. Razor* -Datei eingefügt, sodass Sie in alle *Razor* -Dateien im gleichen Verzeichnis und in untergeordneten Verzeichnissen importiert werden.</span><span class="sxs-lookup"><span data-stu-id="2cc97-203">As seen in the default Blazor projects, it's common to put `@using` directives into a *_Imports.razor* file so that they're imported into all *.razor* files in the same directory and in child directories.</span></span>

<span data-ttu-id="2cc97-204">Wenn sich der Namespace für eine Komponente nicht im Gültigkeitsbereich befindet, können Sie eine Komponente mit dem vollständigen Typnamen wie in c# angeben:</span><span class="sxs-lookup"><span data-stu-id="2cc97-204">If the namespace for a component isn't in scope, you can specify a component using its full type name, as you can in C#:</span></span>

```razor
<MyComponentLib.Counter />
```

## <a name="component-parameters"></a><span data-ttu-id="2cc97-205">Komponentenparameter</span><span class="sxs-lookup"><span data-stu-id="2cc97-205">Component parameters</span></span>

<span data-ttu-id="2cc97-206">In ASP.net Web Forms können Sie mithilfe öffentlicher Eigenschaften Parameter und Daten an Steuerelemente weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="2cc97-206">In ASP.NET Web Forms, you can flow parameters and data to controls using public properties.</span></span> <span data-ttu-id="2cc97-207">Diese Eigenschaften können in Markup mithilfe von Attributen festgelegt oder direkt im Code festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="2cc97-207">These properties can be set in markup using attributes or set directly in code.</span></span> Blazor<span data-ttu-id="2cc97-208">Komponenten funktionieren in ähnlicher Weise, obwohl die Komponenteneigenschaften auch mit dem-Attribut gekennzeichnet werden müssen `[Parameter]` , um als Komponenten Parameter angesehen zu werden.</span><span class="sxs-lookup"><span data-stu-id="2cc97-208"> components work in a similar fashion, although the component properties must also be marked with the `[Parameter]` attribute to be considered component parameters.</span></span>

<span data-ttu-id="2cc97-209">Die folgende `Counter` Komponente definiert einen Komponenten Parameter mit dem Namen `IncrementAmount` , der verwendet werden kann, um den Betrag anzugeben, der bei `Counter` jedem Klicken auf die Schaltfläche erhöht werden soll.</span><span class="sxs-lookup"><span data-stu-id="2cc97-209">The following `Counter` component defines a component parameter called `IncrementAmount` that can be used to specify the amount that the `Counter` should be incremented each time the button is clicked.</span></span>

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

<span data-ttu-id="2cc97-210">Um einen Komponenten Parameter in anzugeben Blazor , verwenden Sie ein Attribut wie in ASP.net Web Forms:</span><span class="sxs-lookup"><span data-stu-id="2cc97-210">To specify a component parameter in Blazor, use an attribute as you would in ASP.NET Web Forms:</span></span>

```razor
<Counter IncrementAmount="10" />
```

## <a name="event-handlers"></a><span data-ttu-id="2cc97-211">Ereignishandler</span><span class="sxs-lookup"><span data-stu-id="2cc97-211">Event handlers</span></span>

<span data-ttu-id="2cc97-212">Beide ASP.net Web Forms und Blazor stellen ein Ereignis basiertes Programmiermodell für die Behandlung von Benutzeroberflächen Ereignissen bereit.</span><span class="sxs-lookup"><span data-stu-id="2cc97-212">Both ASP.NET Web Forms and Blazor provide an event-based programming model for handling UI events.</span></span> <span data-ttu-id="2cc97-213">Beispiele für derartige Ereignisse sind Schaltflächen Klicks und Texteingaben.</span><span class="sxs-lookup"><span data-stu-id="2cc97-213">Examples of such events include button clicks and text input.</span></span> <span data-ttu-id="2cc97-214">In ASP.net Web Forms verwenden Sie HTML-Server Steuerelemente zur Handhabung von Benutzeroberflächen Ereignissen, die vom DOM verfügbar gemacht werden, oder Sie können Ereignisse behandeln, die von Webserver Steuerelementen verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="2cc97-214">In ASP.NET Web Forms, you use HTML server controls to handle UI events exposed by the DOM, or you can handle events exposed by web server controls.</span></span> <span data-ttu-id="2cc97-215">Die Ereignisse werden auf dem Server über Formular-POST Back Anforderungen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="2cc97-215">The events are surfaced on the server through form post-back requests.</span></span> <span data-ttu-id="2cc97-216">Beachten Sie die folgenden Web Forms Schaltflächen-Click-Beispiel:</span><span class="sxs-lookup"><span data-stu-id="2cc97-216">Consider the following Web Forms button click example:</span></span>

<span data-ttu-id="2cc97-217">*Counter. ascx*</span><span class="sxs-lookup"><span data-stu-id="2cc97-217">*Counter.ascx*</span></span>

```aspx-csharp
<asp:Button ID="ClickMeButton" runat="server" Text="Click me!" OnClick="ClickMeButton_Click" />
```

<span data-ttu-id="2cc97-218">*Counter.ascx.cs*</span><span class="sxs-lookup"><span data-stu-id="2cc97-218">*Counter.ascx.cs*</span></span>

```csharp
public partial class Counter : System.Web.UI.UserControl
{
    protected void ClickMeButton_Click(object sender, EventArgs e)
    {
        Console.WriteLine("The button was clicked!");
    }
}
```

<span data-ttu-id="2cc97-219">In Blazor können Sie Handler für DOM-UI-Ereignisse direkt mithilfe von direktivenattributen im Formular registrieren `@on{event}` .</span><span class="sxs-lookup"><span data-stu-id="2cc97-219">In Blazor, you can register handlers for DOM UI events directly using directive attributes of the form `@on{event}`.</span></span> <span data-ttu-id="2cc97-220">Der `{event}` Platzhalter stellt den Namen des Ereignisses dar.</span><span class="sxs-lookup"><span data-stu-id="2cc97-220">The `{event}` placeholder represents the name of the event.</span></span> <span data-ttu-id="2cc97-221">Beispielsweise können Sie auf Schaltflächen Klicks wie folgt lauschen:</span><span class="sxs-lookup"><span data-stu-id="2cc97-221">For example, you can listen for button clicks like this:</span></span>

```razor
<button @onclick="OnClick">Click me!</button>

@code {
    void OnClick()
    {
        Console.WriteLine("The button was clicked!);
    }
}
```

<span data-ttu-id="2cc97-222">Ereignishandler können ein optionales, Ereignis spezifisches Argument akzeptieren, um weitere Informationen zum Ereignis bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="2cc97-222">Event handlers can accept an optional, event-specific argument to provide more information about the event.</span></span> <span data-ttu-id="2cc97-223">Mausereignisse können z. b. ein- `MouseEventArgs` Argument annehmen, aber es ist nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="2cc97-223">For example, mouse events can take a `MouseEventArgs` argument, but it isn't required.</span></span>

```razor
<button @onclick="OnClick">Click me!</button>

@code {
    void OnClick(MouseEventArgs e)
    {
        Console.WriteLine($"Mouse clicked at {e.ScreenX}, {e.ScreenY}.");
    }
}
```

<span data-ttu-id="2cc97-224">Anstatt auf eine Methoden Gruppe für einen Ereignishandler zu verweisen, können Sie einen Lambda-Ausdruck verwenden.</span><span class="sxs-lookup"><span data-stu-id="2cc97-224">Instead of referring to a method group for an event handler, you can use a lambda expression.</span></span> <span data-ttu-id="2cc97-225">Ein Lambda-Ausdruck ermöglicht es Ihnen, andere Werte im Gültigkeitsbereich zu schließen.</span><span class="sxs-lookup"><span data-stu-id="2cc97-225">A lambda expression allows you to close over other in-scope values.</span></span>

```razor
@foreach (var buttonLabel in buttonLabels)
{
    <button @onclick="() => Console.WriteLine($"The {buttonLabel} button was clicked!")">@buttonLabel</button>
}
```

<span data-ttu-id="2cc97-226">Ereignishandler können synchron oder asynchron ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="2cc97-226">Event handlers can execute synchronously or asynchronously.</span></span> <span data-ttu-id="2cc97-227">Der folgende Ereignishandler wird z. b. `OnClick` asynchron ausgeführt:</span><span class="sxs-lookup"><span data-stu-id="2cc97-227">For example, the following `OnClick` event handler executes asynchronously:</span></span>

```razor
<button @onclick="OnClick">Click me!</button>

@code {
    async Task OnClick()
    {
        var result = await Http.GetAsync("api/values");
    }
}
```

<span data-ttu-id="2cc97-228">Nachdem ein Ereignis behandelt wurde, wird die Komponente gerendert, um alle Änderungen des Komponenten Zustands zu berücksichtigen.</span><span class="sxs-lookup"><span data-stu-id="2cc97-228">After an event is handled, the component is rendered to account for any component state changes.</span></span> <span data-ttu-id="2cc97-229">Bei asynchronen Ereignis Handlern wird die Komponente unmittelbar nach Abschluss der handlerausführung gerendert.</span><span class="sxs-lookup"><span data-stu-id="2cc97-229">With asynchronous event handlers, the component is rendered immediately after the handler execution completes.</span></span> <span data-ttu-id="2cc97-230">Die Komponente wird *wieder* gerendert, nachdem der asynchrone Vorgang `Task` abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="2cc97-230">The component is rendered *again* after the asynchronous `Task` completes.</span></span> <span data-ttu-id="2cc97-231">Dieser asynchrone Ausführungs Modus bietet die Möglichkeit, eine geeignete Benutzeroberfläche zu rendereinigen, während der asynchrone Vorgang `Task` noch ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="2cc97-231">This asynchronous execution mode provides an opportunity to render some appropriate UI while the asynchronous `Task` is still in progress.</span></span>

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

<span data-ttu-id="2cc97-232">Komponenten können auch eigene Ereignisse definieren, indem Sie einen Komponenten Parameter vom Typ definieren `EventCallback<TValue>` .</span><span class="sxs-lookup"><span data-stu-id="2cc97-232">Components can also define their own events by defining a component parameter of type `EventCallback<TValue>`.</span></span> <span data-ttu-id="2cc97-233">Ereignis Rückrufe unterstützen alle Variationen von Dom UI-Ereignis Handlern: optionale Argumente, synchrone oder asynchrone Methoden, Methoden Gruppen oder Lambda-Ausdrücke.</span><span class="sxs-lookup"><span data-stu-id="2cc97-233">Event callbacks support all the variations of DOM UI event handlers: optional arguments, synchronous or asynchronous, method groups, or lambda expressions.</span></span>

```razor
<button class="btn btn-primary" @onclick="OnClick">Click me!</button>

@code {
    [Parameter]
    public EventCallback<MouseEventArgs> OnClick { get; set; }
}
```

## <a name="data-binding"></a><span data-ttu-id="2cc97-234">Datenbindung</span><span class="sxs-lookup"><span data-stu-id="2cc97-234">Data binding</span></span>

Blazor<span data-ttu-id="2cc97-235">stellt einen einfachen Mechanismus bereit, mit dem Daten aus einer Benutzeroberflächen Komponente an den Status der Komponente gebunden werden können.</span><span class="sxs-lookup"><span data-stu-id="2cc97-235"> provides a simple mechanism to bind data from a UI component to the component's state.</span></span> <span data-ttu-id="2cc97-236">Diese Vorgehensweise unterscheidet sich von den Features in ASP.net Web Forms für das Binden von Daten aus Datenquellen an UI-Steuerelemente.</span><span class="sxs-lookup"><span data-stu-id="2cc97-236">This approach differs from the features in ASP.NET Web Forms for binding data from data sources to UI controls.</span></span> <span data-ttu-id="2cc97-237">Im Abschnitt [Umgang mit Daten](data.md) wird die Behandlung von Daten aus verschiedenen Datenquellen behandelt.</span><span class="sxs-lookup"><span data-stu-id="2cc97-237">We'll cover handling data from different data sources in the [Dealing with data](data.md) section.</span></span>

<span data-ttu-id="2cc97-238">Verwenden Sie zum Erstellen einer bidirektionalen Datenbindung von einer Benutzeroberflächen Komponente zum Status der Komponente das `@bind` direktivenattribut.</span><span class="sxs-lookup"><span data-stu-id="2cc97-238">To create a two-way data binding from a UI component to the component's state, use the `@bind` directive attribute.</span></span> <span data-ttu-id="2cc97-239">Im folgenden Beispiel ist der Wert des Kontrollkästchens an das- `isChecked` Feld gebunden.</span><span class="sxs-lookup"><span data-stu-id="2cc97-239">In the following example, the value of the check box is bound to the `isChecked` field.</span></span>

```razor
<input type="checkbox" @bind="isChecked" />

@code {
    bool isChecked;
}
```

<span data-ttu-id="2cc97-240">Wenn die Komponente gerendert wird, wird der Wert des Kontrollkästchens auf den Wert des Felds festgelegt `isChecked` .</span><span class="sxs-lookup"><span data-stu-id="2cc97-240">When the component is rendered, the value of the checkbox is set to the value of the `isChecked` field.</span></span> <span data-ttu-id="2cc97-241">Wenn der Benutzer das Kontrollkästchen schaltet, wird das `onchange` -Ereignis ausgelöst, und das `isChecked` Feld wird auf den neuen Wert festgelegt.</span><span class="sxs-lookup"><span data-stu-id="2cc97-241">When the user toggles the checkbox, the `onchange` event is fired and the `isChecked` field is set to the new value.</span></span> <span data-ttu-id="2cc97-242">Die `@bind` Syntax in diesem Fall entspricht dem folgenden Markup:</span><span class="sxs-lookup"><span data-stu-id="2cc97-242">The `@bind` syntax in this case is equivalent to the following markup:</span></span>

```razor
<input value="@isChecked" @onchange="(UIChangeEventArgs e) => isChecked = e.Value" />
```

<span data-ttu-id="2cc97-243">Verwenden Sie das-Attribut, um das für die Bindung verwendete Ereignis zu ändern `@bind:event` .</span><span class="sxs-lookup"><span data-stu-id="2cc97-243">To change the event used for the bind, use the `@bind:event` attribute.</span></span>

```razor
<input @bind="text" @bind:event="oninput" />
<p>@text</p>

@code {
    string text;
}
```

<span data-ttu-id="2cc97-244">Komponenten können auch die Datenbindung an Ihre Parameter unterstützen.</span><span class="sxs-lookup"><span data-stu-id="2cc97-244">Components can also support data binding to their parameters.</span></span> <span data-ttu-id="2cc97-245">Definieren Sie für die Datenbindung einen Ereignis Rückruf Parameter mit dem gleichen Namen wie der bindbare Parameter.</span><span class="sxs-lookup"><span data-stu-id="2cc97-245">To data bind, define an event callback parameter with the same name as the bindable parameter.</span></span> <span data-ttu-id="2cc97-246">Das Suffix "Changed" wird dem Namen hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="2cc97-246">The "Changed" suffix is added to the name.</span></span>

<span data-ttu-id="2cc97-247">*PasswordBox. Razor*</span><span class="sxs-lookup"><span data-stu-id="2cc97-247">*PasswordBox.razor*</span></span>

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

<span data-ttu-id="2cc97-248">Wenn Sie eine Datenbindung an ein zugrunde liegendes UI-Element verketten möchten, legen Sie den Wert fest, und behandeln Sie das Ereignis direkt für das UI-Element, statt das- `@bind` Attribut</span><span class="sxs-lookup"><span data-stu-id="2cc97-248">To chain a data binding to an underlying UI element, set the value and handle the event directly on the UI element instead of using the `@bind` attribute.</span></span>

<span data-ttu-id="2cc97-249">Verwenden Sie zum Binden an einen Komponenten Parameter ein- `@bind-{Parameter}` Attribut, um den Parameter anzugeben, an den die Bindung erfolgen soll.</span><span class="sxs-lookup"><span data-stu-id="2cc97-249">To bind to a component parameter, use a `@bind-{Parameter}` attribute to specify the parameter to which you want to bind.</span></span>

```razor
<PasswordBox @bind-Password="password" />

@code {
    string password;
}
```

## <a name="state-changes"></a><span data-ttu-id="2cc97-250">Statusänderungen</span><span class="sxs-lookup"><span data-stu-id="2cc97-250">State changes</span></span>

<span data-ttu-id="2cc97-251">Wenn sich der Zustand der Komponente außerhalb eines normalen UI-Ereignisses oder Ereignis Rückrufs geändert hat, muss die Komponente manuell signalisieren, dass Sie erneut gerendert werden muss.</span><span class="sxs-lookup"><span data-stu-id="2cc97-251">If the component's state has changed outside of a normal UI event or event callback, then the component must manually signal that it needs to be rendered again.</span></span> <span data-ttu-id="2cc97-252">Um zu signalisieren, dass sich der Status einer Komponente geändert hat, müssen Sie die- `StateHasChanged` Methode für die Komponente aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="2cc97-252">To signal that a component's state has changed, call the `StateHasChanged` method on the component.</span></span>

<span data-ttu-id="2cc97-253">Im folgenden Beispiel zeigt eine Komponente eine Nachricht von einem Dienst an `AppState` , der von anderen Teilen der APP aktualisiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="2cc97-253">In the example below, a component displays a message from an `AppState` service that can be updated by other parts of the app.</span></span> <span data-ttu-id="2cc97-254">Die Komponente registriert die- `StateHasChanged` Methode mit dem- `AppState.OnChange` Ereignis, sodass die Komponente immer dann gerendert wird, wenn die Nachricht aktualisiert wird.</span><span class="sxs-lookup"><span data-stu-id="2cc97-254">The component registers its `StateHasChanged` method with the `AppState.OnChange` event so that the component is rendered whenever the message gets updated.</span></span>

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

## <a name="component-lifecycle"></a><span data-ttu-id="2cc97-255">Komponenten Lebenszyklus</span><span class="sxs-lookup"><span data-stu-id="2cc97-255">Component lifecycle</span></span>

<span data-ttu-id="2cc97-256">Das ASP.net Web Forms Framework verfügt über klar definierte Lebenszyklus Methoden für Module, Seiten und Steuerelemente.</span><span class="sxs-lookup"><span data-stu-id="2cc97-256">The ASP.NET Web Forms framework has well-defined lifecycle methods for modules, pages, and controls.</span></span> <span data-ttu-id="2cc97-257">Das folgende Steuerelement implementiert z. b. Ereignishandler für `Init` das `Load` -,-und- `UnLoad` Lebenszyklus Ereignis:</span><span class="sxs-lookup"><span data-stu-id="2cc97-257">For example, the following control implements event handlers for the `Init`, `Load`, and `UnLoad` lifecycle events:</span></span>

<span data-ttu-id="2cc97-258">*Counter.ascx.cs*</span><span class="sxs-lookup"><span data-stu-id="2cc97-258">*Counter.ascx.cs*</span></span>

```csharp
public partial class Counter : System.Web.UI.UserControl
{
    protected void Page_Init(object sender, EventArgs e) { ... }
    protected void Page_Load(object sender, EventArgs e) { ... }
    protected void Page_UnLoad(object sender, EventArgs e) { ... }
}
```

Blazor<span data-ttu-id="2cc97-259">Komponenten verfügen auch über einen klar definierten Lebenszyklus.</span><span class="sxs-lookup"><span data-stu-id="2cc97-259"> components also have a well-defined lifecycle.</span></span> <span data-ttu-id="2cc97-260">Der Lebenszyklus einer Komponente kann verwendet werden, um den Komponenten Status zu initialisieren und erweiterte Komponenten Verhalten zu implementieren.</span><span class="sxs-lookup"><span data-stu-id="2cc97-260">A component's lifecycle can be used to initialize component state and implement advanced component behaviors.</span></span>

<span data-ttu-id="2cc97-261">Alle Blazor Komponenten Lebenszyklus-Methoden haben synchrone und asynchrone Versionen.</span><span class="sxs-lookup"><span data-stu-id="2cc97-261">All of Blazor's component lifecycle methods have both synchronous and asynchronous versions.</span></span> <span data-ttu-id="2cc97-262">Das Komponenten Rendering ist synchron.</span><span class="sxs-lookup"><span data-stu-id="2cc97-262">Component rendering is synchronous.</span></span> <span data-ttu-id="2cc97-263">Asynchrone Logik kann nicht als Teil des Komponenten Rendering ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="2cc97-263">You can't run asynchronous logic as part of the component rendering.</span></span> <span data-ttu-id="2cc97-264">Alle asynchronen Logik muss als Teil einer `async` Lebenszyklus Methode ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="2cc97-264">All asynchronous logic must execute as part of an `async` lifecycle method.</span></span>

### <a name="oninitialized"></a><span data-ttu-id="2cc97-265">Oninitialisiert</span><span class="sxs-lookup"><span data-stu-id="2cc97-265">OnInitialized</span></span>

<span data-ttu-id="2cc97-266">Die `OnInitialized` -und- `OnInitializedAsync` Methoden werden verwendet, um die Komponente zu initialisieren.</span><span class="sxs-lookup"><span data-stu-id="2cc97-266">The `OnInitialized` and `OnInitializedAsync` methods are used to initialize the component.</span></span> <span data-ttu-id="2cc97-267">Eine Komponente wird in der Regel initialisiert, nachdem Sie erstmals gerendert wurde.</span><span class="sxs-lookup"><span data-stu-id="2cc97-267">A component is typically initialized after it's first rendered.</span></span> <span data-ttu-id="2cc97-268">Nachdem eine Komponente initialisiert wurde, kann Sie mehrmals gerendert werden, bevor Sie schließlich verworfen wird.</span><span class="sxs-lookup"><span data-stu-id="2cc97-268">After a component is initialized, it may be rendered multiple times before it's eventually disposed.</span></span> <span data-ttu-id="2cc97-269">Die `OnInitialized` -Methode ähnelt dem `Page_Load` -Ereignis in ASP.net Web Forms Seiten und Steuerelemente.</span><span class="sxs-lookup"><span data-stu-id="2cc97-269">The `OnInitialized` method is similar to the `Page_Load` event in ASP.NET Web Forms pages and controls.</span></span>

```csharp
protected override void OnInitialized() { ... }
protected override async Task OnInitializedAsync() { await ... }
```

### <a name="onparametersset"></a><span data-ttu-id="2cc97-270">Onparametersset</span><span class="sxs-lookup"><span data-stu-id="2cc97-270">OnParametersSet</span></span>

<span data-ttu-id="2cc97-271">Die `OnParametersSet` -Methode und die- `OnParametersSetAsync` Methode werden aufgerufen, wenn eine Komponente Parameter von ihrem übergeordneten Element erhalten hat und der Wert Eigenschaften zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="2cc97-271">The `OnParametersSet` and `OnParametersSetAsync` methods are called when a component has received parameters from its parent and the value are assigned to properties.</span></span> <span data-ttu-id="2cc97-272">Diese Methoden werden nach der Initialisierung der Komponente und *jedes Mal, wenn die Komponente gerendert wird*, ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="2cc97-272">These methods are executed after component initialization and *each time the component is rendered*.</span></span>

```csharp
protected override void OnParametersSet() { ... }
protected override async Task OnParametersSetAsync() { await ... }
```

### <a name="onafterrender"></a><span data-ttu-id="2cc97-273">Onafterrendering</span><span class="sxs-lookup"><span data-stu-id="2cc97-273">OnAfterRender</span></span>

<span data-ttu-id="2cc97-274">Die `OnAfterRender` -Methode und die- `OnAfterRenderAsync` Methode werden aufgerufen, nachdem eine Komponente das Rendering abgeschlossen hat.</span><span class="sxs-lookup"><span data-stu-id="2cc97-274">The `OnAfterRender` and `OnAfterRenderAsync` methods are called after a component has finished rendering.</span></span> <span data-ttu-id="2cc97-275">Element-und Komponenten Verweise werden an diesem Punkt aufgefüllt (Weitere Informationen zu diesen Konzepten finden Sie unten).</span><span class="sxs-lookup"><span data-stu-id="2cc97-275">Element and component references are populated at this point (more on these concepts below).</span></span> <span data-ttu-id="2cc97-276">Die Interaktivität mit dem Browser ist an diesem Punkt aktiviert.</span><span class="sxs-lookup"><span data-stu-id="2cc97-276">Interactivity with the browser is enabled at this point.</span></span> <span data-ttu-id="2cc97-277">Interaktionen mit der Dom-und JavaScript-Ausführung können problemlos erfolgen.</span><span class="sxs-lookup"><span data-stu-id="2cc97-277">Interactions with the DOM and JavaScript execution can safely take place.</span></span>

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

<span data-ttu-id="2cc97-278">`OnAfterRender`und werden `OnAfterRenderAsync` *nicht aufgerufen, wenn Sie auf dem Server vorab verwendet*werden.</span><span class="sxs-lookup"><span data-stu-id="2cc97-278">`OnAfterRender` and `OnAfterRenderAsync` *aren't called when prerendering on the server*.</span></span>

<span data-ttu-id="2cc97-279">Der- `firstRender` Parameter ist `true` das erste Mal, wenn die Komponente gerendert wird, andernfalls ist der Wert `false` .</span><span class="sxs-lookup"><span data-stu-id="2cc97-279">The `firstRender` parameter is `true` the first time the component is rendered; otherwise, its value is `false`.</span></span>

### <a name="idisposable"></a><span data-ttu-id="2cc97-280">IDisposable</span><span class="sxs-lookup"><span data-stu-id="2cc97-280">IDisposable</span></span>

Blazor<span data-ttu-id="2cc97-281">Komponenten können implementieren `IDisposable` , um Ressourcen freizugeben, wenn die Komponente aus der Benutzeroberfläche entfernt wird.</span><span class="sxs-lookup"><span data-stu-id="2cc97-281"> components can implement `IDisposable` to dispose of resources when the component is removed from the UI.</span></span> <span data-ttu-id="2cc97-282">Eine Razor-Komponente kann `IDispose` mithilfe der- `@implements` Direktive implementiert werden:</span><span class="sxs-lookup"><span data-stu-id="2cc97-282">A Razor component can implement `IDispose` by using the `@implements` directive:</span></span>

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

## <a name="capture-component-references"></a><span data-ttu-id="2cc97-283">Komponenten Verweise erfassen</span><span class="sxs-lookup"><span data-stu-id="2cc97-283">Capture component references</span></span>

<span data-ttu-id="2cc97-284">In ASP.net Web Forms ist es üblich, eine Steuerelement Instanz direkt im Code zu bearbeiten, indem Sie sich auf Ihre ID bezieht.</span><span class="sxs-lookup"><span data-stu-id="2cc97-284">In ASP.NET Web Forms, it's common to manipulate a control instance directly in code by referring to its ID.</span></span> <span data-ttu-id="2cc97-285">In ist Blazor es auch möglich, einen Verweis auf eine Komponente zu erfassen und zu bearbeiten, obwohl Sie viel weniger häufig ist.</span><span class="sxs-lookup"><span data-stu-id="2cc97-285">In Blazor, it's also possible to capture and manipulate a reference to a component, although it's much less common.</span></span>

<span data-ttu-id="2cc97-286">Um einen Komponenten Verweis in zu erfassen Blazor , verwenden Sie das `@ref` direktivenattribut.</span><span class="sxs-lookup"><span data-stu-id="2cc97-286">To capture a component reference in Blazor, use the `@ref` directive attribute.</span></span> <span data-ttu-id="2cc97-287">Der Wert des-Attributs sollte mit dem Namen eines festleg baren Felds mit dem gleichen Typ wie die Komponente übereinstimmen, auf die verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="2cc97-287">The value of the attribute should match the name of a settable field with the same type as the referenced component.</span></span>

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

<span data-ttu-id="2cc97-288">Wenn die übergeordnete Komponente gerendert wird, wird das Feld mit der untergeordneten Komponenteninstanz aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="2cc97-288">When the parent component is rendered, the field is populated with the child component instance.</span></span> <span data-ttu-id="2cc97-289">Anschließend können Sie Methoden für die Komponenteninstanz auf oder anderweitig bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="2cc97-289">You can then call methods on, or otherwise manipulate, the component instance.</span></span>

<span data-ttu-id="2cc97-290">Das direkte Bearbeiten des Komponenten Zustands mithilfe von Komponenten verweisen ist nicht empfehlenswert.</span><span class="sxs-lookup"><span data-stu-id="2cc97-290">Manipulating component state directly using component references isn't recommended.</span></span> <span data-ttu-id="2cc97-291">Dadurch wird verhindert, dass die Komponente automatisch zu den richtigen Zeitpunkten gerendert wird.</span><span class="sxs-lookup"><span data-stu-id="2cc97-291">Doing so prevents the component from being rendered automatically at the correct times.</span></span>

## <a name="capture-element-references"></a><span data-ttu-id="2cc97-292">Element Verweise erfassen</span><span class="sxs-lookup"><span data-stu-id="2cc97-292">Capture element references</span></span>

Blazor<span data-ttu-id="2cc97-293">Komponenten können Verweise auf ein Element erfassen.</span><span class="sxs-lookup"><span data-stu-id="2cc97-293"> components can capture references to an element.</span></span> <span data-ttu-id="2cc97-294">Im Gegensatz zu HTML-Server Steuerelementen in ASP.net-Web Forms können Sie das DOM nicht direkt mithilfe eines Element Verweises in bearbeiten Blazor .</span><span class="sxs-lookup"><span data-stu-id="2cc97-294">Unlike HTML server controls in ASP.NET Web Forms, you can't manipulate the DOM directly using an element reference in Blazor.</span></span> Blazor<span data-ttu-id="2cc97-295">behandelt die meisten Dom-Interaktionen für Sie mit dem Dom-diffingalgorithmus.</span><span class="sxs-lookup"><span data-stu-id="2cc97-295"> handles most DOM interactions for you using its DOM diffing algorithm.</span></span> <span data-ttu-id="2cc97-296">Erfasste Element Verweise in sind nicht transparent Blazor .</span><span class="sxs-lookup"><span data-stu-id="2cc97-296">Captured element references in Blazor are opaque.</span></span> <span data-ttu-id="2cc97-297">Sie werden jedoch verwendet, um einen bestimmten Element Verweis in einem JavaScript-Interop-Befehl zu übergeben.</span><span class="sxs-lookup"><span data-stu-id="2cc97-297">However, they're used to pass a specific element reference in a JavaScript interop call.</span></span> <span data-ttu-id="2cc97-298">Weitere Informationen zum JavaScript-Interop finden Sie unter [ASP.net Core Blazor JavaScript-Interop](/aspnet/core/blazor/javascript-interop).</span><span class="sxs-lookup"><span data-stu-id="2cc97-298">For more information about JavaScript interop, see [ASP.NET Core Blazor JavaScript interop](/aspnet/core/blazor/javascript-interop).</span></span>

## <a name="templated-components"></a><span data-ttu-id="2cc97-299">Komponenten mit Vorlagen</span><span class="sxs-lookup"><span data-stu-id="2cc97-299">Templated components</span></span>

<span data-ttu-id="2cc97-300">In ASP.net Web Forms können Sie Steuer *Elemente*mit Vorlagen erstellen.</span><span class="sxs-lookup"><span data-stu-id="2cc97-300">In ASP.NET Web Forms, you can create *templated controls*.</span></span> <span data-ttu-id="2cc97-301">Mithilfe von Vorlagen basierten Steuerelementen kann der Entwickler einen Teil des HTML-Code angeben, der zum Rendering eines Container Steuer Elements verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="2cc97-301">Templated controls enable the developer to specify a portion of the HTML used to render a container control.</span></span> <span data-ttu-id="2cc97-302">Die Mechanismen der Erstellung von Vorlagen basierten Server Steuerelementen sind komplex, aber Sie ermöglichen leistungsstarke Szenarios zum Rendern von Daten auf Benutzer anpassbare Weise.</span><span class="sxs-lookup"><span data-stu-id="2cc97-302">The mechanics of building templated server controls are complex, but they enable powerful scenarios for rendering data in a user customizable way.</span></span> <span data-ttu-id="2cc97-303">Beispiele für Steuerelemente mit Vorlagen sind `Repeater` und `DataList` .</span><span class="sxs-lookup"><span data-stu-id="2cc97-303">Examples of templated controls include `Repeater` and `DataList`.</span></span>

Blazor<span data-ttu-id="2cc97-304">Komponenten können auch durch Definition von Komponenten Parametern vom Typ oder Vorlagen Weise durch definiert werden `RenderFragment` `RenderFragment<T>` .</span><span class="sxs-lookup"><span data-stu-id="2cc97-304"> components can also be templated by defining component parameters of type `RenderFragment` or `RenderFragment<T>`.</span></span> <span data-ttu-id="2cc97-305">Ein `RenderFragment` stellt einen Block von Razor-Markup dar, der dann von der Komponente gerendert werden kann.</span><span class="sxs-lookup"><span data-stu-id="2cc97-305">A `RenderFragment` represents a chunk of Razor markup that can then be rendered by the component.</span></span> <span data-ttu-id="2cc97-306">Ein `RenderFragment<T>` ist ein Block von Razor-Markup, das einen Parameter annimmt, der beim Rendern des renderfragments angegeben werden kann.</span><span class="sxs-lookup"><span data-stu-id="2cc97-306">A `RenderFragment<T>` is a chunk of Razor markup that takes a parameter that can be specified when the render fragment is rendered.</span></span>

### <a name="child-content"></a><span data-ttu-id="2cc97-307">Untergeordneter Inhalt</span><span class="sxs-lookup"><span data-stu-id="2cc97-307">Child content</span></span>

Blazor<span data-ttu-id="2cc97-308">Komponenten können ihren untergeordneten Inhalt als einen erfassen `RenderFragment` und diesen Inhalt als Teil des Komponenten Rendering rendern.</span><span class="sxs-lookup"><span data-stu-id="2cc97-308"> components can capture their child content as a `RenderFragment` and render that content as part of the component rendering.</span></span> <span data-ttu-id="2cc97-309">Zum Erfassen von untergeordnetem Inhalt definieren Sie einen Komponenten Parameter vom Typ, `RenderFragment` und benennen Sie ihn `ChildContent` .</span><span class="sxs-lookup"><span data-stu-id="2cc97-309">To capture child content, define a component parameter of type `RenderFragment` and name it `ChildContent`.</span></span>

<span data-ttu-id="2cc97-310">*Childcontentcomponent. Razor*</span><span class="sxs-lookup"><span data-stu-id="2cc97-310">*ChildContentComponent.razor*</span></span>

```razor
<h1>Component with child content</h1>

<div>@ChildContent</div>

@code {
    [Parameter]
    public RenderFragment ChildContent { get; set; }
}
```

<span data-ttu-id="2cc97-311">Eine übergeordnete Komponente kann dann untergeordneten Inhalt mithilfe von normalem Razor-Syntax bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="2cc97-311">A parent component can then supply child content using normal Razor syntax.</span></span>

```razor
<ChildContentComponent>
    <p>The time is @DateTime.Now</p>
</ChildContentComponent>
```

### <a name="template-parameters"></a><span data-ttu-id="2cc97-312">Vorlagenparameter</span><span class="sxs-lookup"><span data-stu-id="2cc97-312">Template parameters</span></span>

<span data-ttu-id="2cc97-313">Eine auf Vorlagen basierende Blazor Komponente kann auch mehrere Komponenten Parameter vom Typ `RenderFragment` oder definieren `RenderFragment<T>` .</span><span class="sxs-lookup"><span data-stu-id="2cc97-313">A templated Blazor component can also define multiple component parameters of type `RenderFragment` or `RenderFragment<T>`.</span></span> <span data-ttu-id="2cc97-314">Der-Parameter für einen `RenderFragment<T>` kann angegeben werden, wenn er aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="2cc97-314">The parameter for a `RenderFragment<T>` can be specified when it's invoked.</span></span> <span data-ttu-id="2cc97-315">Um einen generischen Typparameter für eine Komponente anzugeben, verwenden Sie die `@typeparam` Razor-Direktive.</span><span class="sxs-lookup"><span data-stu-id="2cc97-315">To specify a generic type parameter for a component, use the `@typeparam` Razor directive.</span></span>

<span data-ttu-id="2cc97-316">*Simplelistview. Razor*</span><span class="sxs-lookup"><span data-stu-id="2cc97-316">*SimpleListView.razor*</span></span>

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

<span data-ttu-id="2cc97-317">Wenn Sie eine auf Vorlagen basierende Komponente verwenden, können die Vorlagen Parameter mit untergeordneten Elementen angegeben werden, die den Namen der Parameter entsprechen.</span><span class="sxs-lookup"><span data-stu-id="2cc97-317">When using a templated component, the template parameters can be specified using child elements that match the names of the parameters.</span></span> <span data-ttu-id="2cc97-318">Komponenten Argumente vom Typ, `RenderFragment<T>` die als-Elemente übergeben werden, haben einen impliziten Parameter mit dem Namen `context`</span><span class="sxs-lookup"><span data-stu-id="2cc97-318">Component arguments of type `RenderFragment<T>` passed as elements have an implicit parameter named `context`.</span></span> <span data-ttu-id="2cc97-319">Sie können den Namen dieses implementierenden Parameters mithilfe des- `Context` Attributs für das untergeordnete-Element ändern.</span><span class="sxs-lookup"><span data-stu-id="2cc97-319">You can change the name of this implement parameter using the `Context` attribute on the child element.</span></span> <span data-ttu-id="2cc97-320">Alle generischen Typparameter können mithilfe eines Attributs angegeben werden, das mit dem Namen des Typparameters übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="2cc97-320">Any generic type parameters can be specified using an attribute that matches the name of the type parameter.</span></span> <span data-ttu-id="2cc97-321">Der Typparameter wird nach Möglichkeit abgeleitet:</span><span class="sxs-lookup"><span data-stu-id="2cc97-321">The type parameter will be inferred if possible:</span></span>

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

<span data-ttu-id="2cc97-322">Die Ausgabe dieser Komponente sieht wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="2cc97-322">The output of this component looks like this:</span></span>

```html
<h1>My list</h1>
<ul>
    <li><p>The message is: message1</p></li>
    <li><p>The message is: message2</p></li>
<ul>
```

## <a name="code-behind"></a><span data-ttu-id="2cc97-323">CodeBehind</span><span class="sxs-lookup"><span data-stu-id="2cc97-323">Code-behind</span></span>

<span data-ttu-id="2cc97-324">Eine Blazor Komponente wird in der Regel in einer einzelnen *Razor* -Datei erstellt.</span><span class="sxs-lookup"><span data-stu-id="2cc97-324">A Blazor component is typically authored in a single *.razor* file.</span></span> <span data-ttu-id="2cc97-325">Es ist jedoch auch möglich, den Code und das Markup mithilfe einer Code Behind-Datei zu trennen.</span><span class="sxs-lookup"><span data-stu-id="2cc97-325">However, it's also possible to separate the code and markup using a code-behind file.</span></span> <span data-ttu-id="2cc97-326">Um eine Komponenten Datei zu verwenden, fügen Sie eine c#-Datei hinzu, die mit dem Dateinamen der Komponenten Datei übereinstimmt, jedoch mit einer hinzugefügten Erweiterung *. cs* (*counter.Razor.cs*).</span><span class="sxs-lookup"><span data-stu-id="2cc97-326">To use a component file, add a C# file that matches the file name of the component file but with a *.cs* extension added (*Counter.razor.cs*).</span></span> <span data-ttu-id="2cc97-327">Verwenden Sie die c#-Datei, um eine Basisklasse für die Komponente zu definieren.</span><span class="sxs-lookup"><span data-stu-id="2cc97-327">Use the C# file to define a base class for the component.</span></span> <span data-ttu-id="2cc97-328">Sie können der Basisklasse einen beliebigen Namen benennen, aber es ist üblich, die Klasse mit der Komponenten Klasse zu benennen, aber mit einer `Base` Erweiterung hinzugefügt ( `CounterBase` ).</span><span class="sxs-lookup"><span data-stu-id="2cc97-328">You can name the base class anything you'd like, but it's common to name the class the same as the component class, but with a `Base` extension added (`CounterBase`).</span></span> <span data-ttu-id="2cc97-329">Die komponentenbasierte Klasse muss auch von abgeleitet werden `ComponentBase` .</span><span class="sxs-lookup"><span data-stu-id="2cc97-329">The component-based class must also derive from `ComponentBase`.</span></span> <span data-ttu-id="2cc97-330">Fügen Sie dann in der Razor-Komponenten Datei die- `@inherits` Direktive hinzu, um die Basisklasse für die Komponente ( `@inherits CounterBase` ) anzugeben.</span><span class="sxs-lookup"><span data-stu-id="2cc97-330">Then, in the Razor component file, add the `@inherits` directive to specify the base class for the component (`@inherits CounterBase`).</span></span>

<span data-ttu-id="2cc97-331">*Counter. Razor*</span><span class="sxs-lookup"><span data-stu-id="2cc97-331">*Counter.razor*</span></span>

```razor
@inherits CounterBase

<h1>Counter</h1>

<p>Current count: @currentCount</p>

<button @onclick="IncrementCount">Click me</button>
```

<span data-ttu-id="2cc97-332">*Counter.razor.cs*</span><span class="sxs-lookup"><span data-stu-id="2cc97-332">*Counter.razor.cs*</span></span>

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

<span data-ttu-id="2cc97-333">Die Sichtbarkeit der Komponenten Elemente in der Basisklasse muss oder sein, um `protected` `public` für die Komponenten Klasse sichtbar zu sein.</span><span class="sxs-lookup"><span data-stu-id="2cc97-333">The visibility of the component's members in the base class must be `protected` or `public` to be visible to the component class.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="2cc97-334">Zusätzliche Ressourcen</span><span class="sxs-lookup"><span data-stu-id="2cc97-334">Additional resources</span></span>

<span data-ttu-id="2cc97-335">Die vorhergehende Behandlung aller Aspekte von Komponenten ist nicht vollständig Blazor .</span><span class="sxs-lookup"><span data-stu-id="2cc97-335">The preceding isn't an exhaustive treatment of all aspects of Blazor components.</span></span> <span data-ttu-id="2cc97-336">Weitere Informationen zum [Erstellen und Verwenden von ASP.net Core Razor-Komponenten](/aspnet/core/blazor/components)finden Sie in der Blazor Dokumentation zu.</span><span class="sxs-lookup"><span data-stu-id="2cc97-336">For more information on how to [Create and use ASP.NET Core Razor components](/aspnet/core/blazor/components), see the Blazor documentation.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="2cc97-337">[Zurück](app-startup.md)
>[Weiter](pages-routing-layouts.md)</span><span class="sxs-lookup"><span data-stu-id="2cc97-337">[Previous](app-startup.md)
[Next](pages-routing-layouts.md)</span></span>
