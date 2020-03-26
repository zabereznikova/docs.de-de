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
# <a name="build-reusable-ui-components-with-blazor"></a><span data-ttu-id="85be4-103">Erstellen wiederverwendbarer UI-Komponenten mit Blazor</span><span class="sxs-lookup"><span data-stu-id="85be4-103">Build reusable UI components with Blazor</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="85be4-104">Eines der schönsten Dinge an ASP.NET Web Forms ist, wie es die Verkapselung von wiederverwendbaren Teilen von Benutzeroberflächencode in wiederverwendbare UI-Steuerelemente ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="85be4-104">One of the beautiful things about ASP.NET Web Forms is how it enables encapsulation of reusable pieces of user interface (UI) code into reusable UI controls.</span></span> <span data-ttu-id="85be4-105">Benutzerdefinierte Benutzersteuerelemente können in Markup mithilfe von *.ascx-Dateien* definiert werden.</span><span class="sxs-lookup"><span data-stu-id="85be4-105">Custom user controls can be defined in markup using *.ascx* files.</span></span> <span data-ttu-id="85be4-106">Sie können auch ausgeklügelte Serversteuerelemente in Code mit vollständiger Designerunterstützung erstellen.</span><span class="sxs-lookup"><span data-stu-id="85be4-106">You can also build elaborate server controls in code with full designer support.</span></span>

<span data-ttu-id="85be4-107">Blazor unterstützt auch die UI-Kapselung durch *Komponenten*.</span><span class="sxs-lookup"><span data-stu-id="85be4-107">Blazor also supports UI encapsulation through *components*.</span></span> <span data-ttu-id="85be4-108">Eine Komponente:</span><span class="sxs-lookup"><span data-stu-id="85be4-108">A component:</span></span>

- <span data-ttu-id="85be4-109">Ein eigenständiger Teil der Benutzeroberfläche.</span><span class="sxs-lookup"><span data-stu-id="85be4-109">Is a self-contained chunk of UI.</span></span>
- <span data-ttu-id="85be4-110">Behält seinen eigenen Status und seine Renderinglogik bei.</span><span class="sxs-lookup"><span data-stu-id="85be4-110">Maintains its own state and rendering logic.</span></span>
- <span data-ttu-id="85be4-111">Kann UI-Ereignishandler definieren, an Eingabedaten binden und seinen eigenen Lebenszyklus verwalten.</span><span class="sxs-lookup"><span data-stu-id="85be4-111">Can define UI event handlers, bind to input data, and manage its own lifecycle.</span></span>
- <span data-ttu-id="85be4-112">Wird in der Regel in einer *.razor-Datei* mit Razor-Syntax definiert.</span><span class="sxs-lookup"><span data-stu-id="85be4-112">Is typically defined in a *.razor* file using Razor syntax.</span></span>

## <a name="an-introduction-to-razor"></a><span data-ttu-id="85be4-113">Eine Einführung in Razor</span><span class="sxs-lookup"><span data-stu-id="85be4-113">An introduction to Razor</span></span>

<span data-ttu-id="85be4-114">Razor ist eine leichtgewichtige Markup-Tempor-Sprache, die auf HTML und C- basiert.</span><span class="sxs-lookup"><span data-stu-id="85be4-114">Razor is a light-weight markup templating language based on HTML and C#.</span></span> <span data-ttu-id="85be4-115">Mit Razor können Sie nahtlos zwischen Markup und C-Code wechseln, um die Renderlogik Ihrer Komponente zu definieren.</span><span class="sxs-lookup"><span data-stu-id="85be4-115">With Razor, you can seamlessly transition between markup and C# code to define your component rendering logic.</span></span> <span data-ttu-id="85be4-116">Wenn die *.razor-Datei* kompiliert wird, wird die Renderinglogik strukturiert in einer .NET-Klasse erfasst.</span><span class="sxs-lookup"><span data-stu-id="85be4-116">When the *.razor* file is compiled, the rendering logic is captured in a structured way in a .NET class.</span></span> <span data-ttu-id="85be4-117">Der Name der kompilierten Klasse wird dem *.razor-Dateinamen* entnommen.</span><span class="sxs-lookup"><span data-stu-id="85be4-117">The name of the compiled class is taken from the *.razor* file name.</span></span> <span data-ttu-id="85be4-118">Der Namespace wird aus dem Standardnamespace für das Projekt und den Ordnerpfad `@namespace` entnommen, oder Sie können den Namespace mithilfe der Direktive explizit angeben (mehr zu Razor-Direktiven unten).</span><span class="sxs-lookup"><span data-stu-id="85be4-118">The namespace is taken from the default namespace for the project and the folder path, or you can explicitly specify the namespace using the `@namespace` directive (more on Razor directives below).</span></span>

<span data-ttu-id="85be4-119">Die Renderinglogik einer Komponente wird mit normalem HTML-Markup erstellt, wobei die dynamische Logik mit c' hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="85be4-119">A component's rendering logic is authored using normal HTML markup with dynamic logic added using C#.</span></span> <span data-ttu-id="85be4-120">Das `@` Zeichen wird für den Übergang zu C- verwendet.</span><span class="sxs-lookup"><span data-stu-id="85be4-120">The `@` character is used to transition to C#.</span></span> <span data-ttu-id="85be4-121">Razor ist in der Regel intelligent, wenn Sie wieder zu HTML gewechselt haben.</span><span class="sxs-lookup"><span data-stu-id="85be4-121">Razor is typically smart about figuring out when you've switched back to HTML.</span></span> <span data-ttu-id="85be4-122">Die folgende Komponente rendert `<p>` z. B. ein Tag mit der aktuellen Uhrzeit:</span><span class="sxs-lookup"><span data-stu-id="85be4-122">For example, the following component renders a `<p>` tag with the current time:</span></span>

```razor
<p>@DateTime.Now</p>
```

<span data-ttu-id="85be4-123">Um explizit den Anfang und die Endung eines C-Ausdrucks anzugeben, verwenden Sie Klammern:</span><span class="sxs-lookup"><span data-stu-id="85be4-123">To explicitly specify the beginning and ending of a C# expression, use parentheses:</span></span>

```razor
<p>@(DateTime.Now)</p>
```

<span data-ttu-id="85be4-124">Razor erleichtert auch die Verwendung des Steuerungsflusses von C- in Ihrer Renderinglogik.</span><span class="sxs-lookup"><span data-stu-id="85be4-124">Razor also makes it easy to use C# control flow in your rendering logic.</span></span> <span data-ttu-id="85be4-125">Sie können z. B. einige HTML-Codes bedingt wie folgt rendern:</span><span class="sxs-lookup"><span data-stu-id="85be4-125">For example, you can conditionally render some HTML like this:</span></span>

```razor
@if (value % 2 == 0)
{
    <p>The value was even.</p>
}
```

<span data-ttu-id="85be4-126">Sie können auch eine Liste von Elementen `foreach` generieren, die eine normale C-Schleife wie folgt verwenden:</span><span class="sxs-lookup"><span data-stu-id="85be4-126">Or you can generate a list of items using a normal C# `foreach` loop like this:</span></span>

```razor
<ul>
@foreach (var item in items)
{
    <li>@item.Text</li>
}
</ul>
```

<span data-ttu-id="85be4-127">Razor-Direktiven, wie Direktiven in ASP.NET Web Forms, steuern viele Aspekte, wie eine Razor-Komponente kompiliert wird.</span><span class="sxs-lookup"><span data-stu-id="85be4-127">Razor directives, like directives in ASP.NET Web Forms, control many aspects of how a Razor component is compiled.</span></span> <span data-ttu-id="85be4-128">Beispiele hierfür sind die Komponenten:</span><span class="sxs-lookup"><span data-stu-id="85be4-128">Examples include the component's:</span></span>

- <span data-ttu-id="85be4-129">Namespace</span><span class="sxs-lookup"><span data-stu-id="85be4-129">Namespace</span></span>
- <span data-ttu-id="85be4-130">Basisklasse</span><span class="sxs-lookup"><span data-stu-id="85be4-130">Base class</span></span>
- <span data-ttu-id="85be4-131">Implementierte Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="85be4-131">Implemented interfaces</span></span>
- <span data-ttu-id="85be4-132">Generische Parameter</span><span class="sxs-lookup"><span data-stu-id="85be4-132">Generic parameters</span></span>
- <span data-ttu-id="85be4-133">Importierte Namespaces</span><span class="sxs-lookup"><span data-stu-id="85be4-133">Imported namespaces</span></span>
- <span data-ttu-id="85be4-134">Routen</span><span class="sxs-lookup"><span data-stu-id="85be4-134">Routes</span></span>

<span data-ttu-id="85be4-135">Razor-Direktiven `@` beginnen mit dem Zeichen und werden in der Regel am Anfang einer neuen Zeile am Anfang der Datei verwendet.</span><span class="sxs-lookup"><span data-stu-id="85be4-135">Razor directives start with the `@` character and are typically used at the start of a new line at the start of the file.</span></span> <span data-ttu-id="85be4-136">Die `@namespace` Direktive definiert z. B. den Namespace der Komponente:</span><span class="sxs-lookup"><span data-stu-id="85be4-136">For example, the `@namespace` directive defines the component's namespace:</span></span>

```razor
@namespace MyComponentNamespace
```

<span data-ttu-id="85be4-137">In der folgenden Tabelle werden die verschiedenen Razor-Direktiven zusammengefasst, die in Blazor verwendet werden, sowie deren ASP.NET Web Forms-Äquivalente, sofern vorhanden.</span><span class="sxs-lookup"><span data-stu-id="85be4-137">The following table summarizes the various Razor directives used in Blazor and their ASP.NET Web Forms equivalents, if they exist.</span></span>

|<span data-ttu-id="85be4-138">Direktive</span><span class="sxs-lookup"><span data-stu-id="85be4-138">Directive</span></span>    |<span data-ttu-id="85be4-139">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="85be4-139">Description</span></span>|<span data-ttu-id="85be4-140">Beispiel</span><span class="sxs-lookup"><span data-stu-id="85be4-140">Example</span></span>|<span data-ttu-id="85be4-141">Web Forms-Äquivalent</span><span class="sxs-lookup"><span data-stu-id="85be4-141">Web Forms equivalent</span></span>|
|-------------|-----------|-------|--------------------|
|`@attribute` |<span data-ttu-id="85be4-142">Fügt der Komponente ein Attribut auf Klassenebene hinzu</span><span class="sxs-lookup"><span data-stu-id="85be4-142">Adds a class-level attribute to the component</span></span>|`@attribute [Authorize]`|<span data-ttu-id="85be4-143">Keine</span><span class="sxs-lookup"><span data-stu-id="85be4-143">None</span></span>|
|`@code`      |<span data-ttu-id="85be4-144">Fügt der Komponente Klassenmember hinzu</span><span class="sxs-lookup"><span data-stu-id="85be4-144">Adds class members to the component</span></span>|`@code { ... }`|`<script runat="server">...</script>`|
|`@implements`|<span data-ttu-id="85be4-145">Implementiert die angegebene Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="85be4-145">Implements the specified interface</span></span>|`@implements IDisposable`|<span data-ttu-id="85be4-146">Verwenden des CodeBehinds</span><span class="sxs-lookup"><span data-stu-id="85be4-146">Use code-behind</span></span>|
|`@inherits`  |<span data-ttu-id="85be4-147">Erbt von der angegebenen Basisklasse</span><span class="sxs-lookup"><span data-stu-id="85be4-147">Inherits from the specified base class</span></span>|`@inherits MyComponentBase`|`<%@ Control Inherits="MyUserControlBase" %>`|
|`@inject`    |<span data-ttu-id="85be4-148">Injiziert einen Dienst in die Komponente</span><span class="sxs-lookup"><span data-stu-id="85be4-148">Injects a service into the component</span></span>|`@inject IJSRuntime JS`|<span data-ttu-id="85be4-149">Keine</span><span class="sxs-lookup"><span data-stu-id="85be4-149">None</span></span>|
|`@layout`    |<span data-ttu-id="85be4-150">Gibt eine Layoutkomponente für die Komponente an</span><span class="sxs-lookup"><span data-stu-id="85be4-150">Specifies a layout component for the component</span></span>|`@layout MainLayout`|`<%@ Page MasterPageFile="~/Site.Master" %>`|
|`@namespace` |<span data-ttu-id="85be4-151">Legt den Namespace für die Komponente fest</span><span class="sxs-lookup"><span data-stu-id="85be4-151">Sets the namespace for the component</span></span>|`@namespace MyNamespace`|<span data-ttu-id="85be4-152">Keine</span><span class="sxs-lookup"><span data-stu-id="85be4-152">None</span></span>|
|`@page`      |<span data-ttu-id="85be4-153">Gibt die Route für die Komponente an</span><span class="sxs-lookup"><span data-stu-id="85be4-153">Specifies the route for the component</span></span>|`@page "/product/{id}"`|`<%@ Page %>`|
|`@typeparam` |<span data-ttu-id="85be4-154">Gibt einen generischen Typparameter für die Komponente an.</span><span class="sxs-lookup"><span data-stu-id="85be4-154">Specifies a generic type parameter for the component</span></span>|`@typeparam TItem`|<span data-ttu-id="85be4-155">Verwenden des CodeBehinds</span><span class="sxs-lookup"><span data-stu-id="85be4-155">Use code-behind</span></span>|
|`@using`     |<span data-ttu-id="85be4-156">Gibt einen Namespace an, der in den Bereich eingebracht werden soll.</span><span class="sxs-lookup"><span data-stu-id="85be4-156">Specifies a namespace to bring into scope</span></span>|`@using MyComponentNamespace`|<span data-ttu-id="85be4-157">Hinzufügen von Namespace in *web.config*</span><span class="sxs-lookup"><span data-stu-id="85be4-157">Add namespace in *web.config*</span></span>|

<span data-ttu-id="85be4-158">Razor-Komponenten verwenden außerdem umfangreiche *Direktivenattribute* für Elemente, um verschiedene Aspekte der Kompilierung von Komponenten zu steuern (Ereignisbehandlung, Datenbindung, Komponenten- & Elementreferenzen usw.).</span><span class="sxs-lookup"><span data-stu-id="85be4-158">Razor components also make extensive use of *directive attributes* on elements to control various aspects of how components get compiled (event handling, data binding, component & element references, and so on).</span></span> <span data-ttu-id="85be4-159">Direktive-Attribute folgen alle einer allgemeinen generischen Syntax, bei der die Werte in Klammern optional sind:</span><span class="sxs-lookup"><span data-stu-id="85be4-159">Directive attributes all follow a common generic syntax where the values in parenthesis are optional:</span></span>

```razor
@directive(-suffix(:name))(="value")
```

<span data-ttu-id="85be4-160">In der folgenden Tabelle werden die verschiedenen Attribute für Razor-Direktiven zusammengefasst, die in Blazor verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="85be4-160">The following table summarizes the various attributes for Razor directives used in Blazor.</span></span>

|<span data-ttu-id="85be4-161">Attribut</span><span class="sxs-lookup"><span data-stu-id="85be4-161">Attribute</span></span>    |<span data-ttu-id="85be4-162">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="85be4-162">Description</span></span>|<span data-ttu-id="85be4-163">Beispiel</span><span class="sxs-lookup"><span data-stu-id="85be4-163">Example</span></span>|
|-------------|-----------|-------|
|`@attributes`|<span data-ttu-id="85be4-164">Rendert ein Wörterbuch mit Attributen</span><span class="sxs-lookup"><span data-stu-id="85be4-164">Renders a dictionary of attributes</span></span>|`<input @attributes="ExtraAttributes" />`|
|`@bind`      |<span data-ttu-id="85be4-165">Erstellt eine zweiseitige Datenbindung</span><span class="sxs-lookup"><span data-stu-id="85be4-165">Creates a two-way data binding</span></span>    |`<input @bind="username" @bind:event="oninput" />`|
|`@on{event}` |<span data-ttu-id="85be4-166">Fügt einen Ereignishandler für das angegebene Ereignis hinzu</span><span class="sxs-lookup"><span data-stu-id="85be4-166">Adds an event handler for the specified event</span></span>|`<button @onclick="IncrementCount">Click me!</button>`|
|`@key`       |<span data-ttu-id="85be4-167">Gibt einen Schlüssel an, der vom Diffingalgorithmus zum Beibehalten von Elementen in einer Auflistung verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="85be4-167">Specifies a key to be used by the diffing algorithm for preserving elements in a collection</span></span>|`<DetailsEditor @key="person" Details="person.Details" />`|
|`@ref`       |<span data-ttu-id="85be4-168">Erfasst einen Verweis auf die Komponente oder das HTML-Element</span><span class="sxs-lookup"><span data-stu-id="85be4-168">Captures a reference to the component or HTML element</span></span>|`<MyDialog @ref="myDialog" />`|

<span data-ttu-id="85be4-169">Die verschiedenen Direktivenattribute,`@onclick`die `@bind` `@ref`von Blazor ( , , usw.) verwendet werden, werden in den folgenden Abschnitten und späteren Kapiteln behandelt.</span><span class="sxs-lookup"><span data-stu-id="85be4-169">The various directive attributes used by Blazor (`@onclick`, `@bind`, `@ref`, and so on) are covered in the sections below and later chapters.</span></span>

<span data-ttu-id="85be4-170">Viele der Syntaxen, die in *.aspx-* und *.ascx-Dateien* verwendet werden, weisen parallele Syntaxen in Razor auf.</span><span class="sxs-lookup"><span data-stu-id="85be4-170">Many of the syntaxes used in *.aspx* and *.ascx* files have parallel syntaxes in Razor.</span></span> <span data-ttu-id="85be4-171">Im Folgenden finden Sie einen einfachen Vergleich der Syntaxen für ASP.NET Web Forms und Razor.</span><span class="sxs-lookup"><span data-stu-id="85be4-171">Below is a simple comparison of the syntaxes for ASP.NET Web Forms and Razor.</span></span>

|<span data-ttu-id="85be4-172">Funktion</span><span class="sxs-lookup"><span data-stu-id="85be4-172">Feature</span></span>                      |<span data-ttu-id="85be4-173">Web Forms</span><span class="sxs-lookup"><span data-stu-id="85be4-173">Web Forms</span></span>           |<span data-ttu-id="85be4-174">Syntax</span><span class="sxs-lookup"><span data-stu-id="85be4-174">Syntax</span></span>               |<span data-ttu-id="85be4-175">Razor</span><span class="sxs-lookup"><span data-stu-id="85be4-175">Razor</span></span>         |<span data-ttu-id="85be4-176">Syntax</span><span class="sxs-lookup"><span data-stu-id="85be4-176">Syntax</span></span> |
|-----------------------------|--------------------|---------------------|--------------|-------|
|<span data-ttu-id="85be4-177">Anweisungen</span><span class="sxs-lookup"><span data-stu-id="85be4-177">Directives</span></span>                   |`<%@ [directive] %>`|`<%@ Page %>`        |`@[directive]`|`@page`|
|<span data-ttu-id="85be4-178">Codeblöcke</span><span class="sxs-lookup"><span data-stu-id="85be4-178">Code blocks</span></span>                  |`<% %>`             |`<% int x = 123; %>` |`@{ }`        |`@{ int x = 123; }`|
|<span data-ttu-id="85be4-179">Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="85be4-179">Expressions</span></span><br><span data-ttu-id="85be4-180">(HTML-kodiert)</span><span class="sxs-lookup"><span data-stu-id="85be4-180">(HTML-encoded)</span></span>|`<%: %>`            |`<%:DateTime.Now %>` |<span data-ttu-id="85be4-181">Implizite:`@`</span><span class="sxs-lookup"><span data-stu-id="85be4-181">Implicit: `@`</span></span><br><span data-ttu-id="85be4-182">explizit:`@()`</span><span class="sxs-lookup"><span data-stu-id="85be4-182">Explicit: `@()`</span></span>|`@DateTime.Now`<br>`@(DateTime.Now)`|
|<span data-ttu-id="85be4-183">Kommentare</span><span class="sxs-lookup"><span data-stu-id="85be4-183">Comments</span></span>                     |`<%-- --%>`         |`<%-- Commented --%>`|`@* *@`       |`@* Commented *@`|
|<span data-ttu-id="85be4-184">Datenbindung</span><span class="sxs-lookup"><span data-stu-id="85be4-184">Data binding</span></span>                 |`<%# %>`            |`<%# Bind("Name") %>`|`@bind`       |`<input @bind="username" />`|

<span data-ttu-id="85be4-185">Um der Razor-Komponentenklasse Member `@code` hinzuzufügen, verwenden Sie die Direktive.</span><span class="sxs-lookup"><span data-stu-id="85be4-185">To add members to the Razor component class, use the `@code` directive.</span></span> <span data-ttu-id="85be4-186">Diese Technik ähnelt der `<script runat="server">...</script>` Verwendung eines Blocks in einem ASP.NET Web Forms-Benutzersteuerelement oder einer Seite.</span><span class="sxs-lookup"><span data-stu-id="85be4-186">This technique is similar to using a `<script runat="server">...</script>` block in an ASP.NET Web Forms user control or page.</span></span>

```razor
@code {
    int count = 0;

    void IncrementCount()
    {
        count++;
    }
}
```

<span data-ttu-id="85be4-187">Da Razor auf C-Code basiert, muss es aus einem C-Projekt kompiliert werden (*.csproj*).</span><span class="sxs-lookup"><span data-stu-id="85be4-187">Because Razor is based on C#, it must be compiled from within a C# project (*.csproj*).</span></span> <span data-ttu-id="85be4-188">Sie können *.razor-Dateien* nicht aus einem Visual Basic-Projekt kompilieren (*.vbproj*).</span><span class="sxs-lookup"><span data-stu-id="85be4-188">You can't compile *.razor* files from a Visual Basic project (*.vbproj*).</span></span> <span data-ttu-id="85be4-189">Sie können weiterhin auf Visual Basic-Projekte aus Ihrem Blazor-Projekt verweisen.</span><span class="sxs-lookup"><span data-stu-id="85be4-189">You can still reference Visual Basic projects from your Blazor project.</span></span> <span data-ttu-id="85be4-190">Auch das Gegenteil ist der Fall.</span><span class="sxs-lookup"><span data-stu-id="85be4-190">The opposite is true too.</span></span>

<span data-ttu-id="85be4-191">Eine vollständige Razor-Syntaxreferenz finden Sie unter [Razor-Syntaxreferenz für ASP.NET Core](/aspnet/core/mvc/views/razor).</span><span class="sxs-lookup"><span data-stu-id="85be4-191">For a full Razor syntax reference, see [Razor syntax reference for ASP.NET Core](/aspnet/core/mvc/views/razor).</span></span>

## <a name="use-components"></a><span data-ttu-id="85be4-192">Verwenden von Komponenten</span><span class="sxs-lookup"><span data-stu-id="85be4-192">Use components</span></span>

<span data-ttu-id="85be4-193">Neben normalem HTML können Komponenten auch andere Komponenten als Teil ihrer Renderinglogik verwenden.</span><span class="sxs-lookup"><span data-stu-id="85be4-193">Aside from normal HTML, components can also use other components as part of their rendering logic.</span></span> <span data-ttu-id="85be4-194">Die Syntax für die Verwendung einer Komponente in Razor ähnelt der Verwendung eines Benutzersteuerelements in einer ASP.NET Web Forms-App.</span><span class="sxs-lookup"><span data-stu-id="85be4-194">The syntax for using a component in Razor is similar to using a user control in an ASP.NET Web Forms app.</span></span> <span data-ttu-id="85be4-195">Komponenten werden mithilfe eines Element-Tags angegeben, das mit dem Typnamen der Komponente übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="85be4-195">Components are specified using an element tag that matches the type name of the component.</span></span> <span data-ttu-id="85be4-196">Sie können z. `Counter` B. eine Komponente wie die folgende hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="85be4-196">For example, you can add a `Counter` component like this:</span></span>

```razor
<Counter />
```

<span data-ttu-id="85be4-197">Im Gegensatz zu ASP.NET Web Forms, Komponenten in Blazor:</span><span class="sxs-lookup"><span data-stu-id="85be4-197">Unlike ASP.NET Web Forms, components in Blazor:</span></span>

- <span data-ttu-id="85be4-198">Verwenden Sie kein Elementpräfix (z. B. `asp:`).</span><span class="sxs-lookup"><span data-stu-id="85be4-198">Don't use an element prefix (for example, `asp:`).</span></span>
- <span data-ttu-id="85be4-199">Erfordern Sie keine Registrierung auf der Seite oder in der *web.config*.</span><span class="sxs-lookup"><span data-stu-id="85be4-199">Don't require registration on the page or in the *web.config*.</span></span>

<span data-ttu-id="85be4-200">Denken Sie an Razor-Komponenten wie .NET-Typen, denn genau das sind sie.</span><span class="sxs-lookup"><span data-stu-id="85be4-200">Think of Razor components like you would .NET types, because that's exactly what they are.</span></span> <span data-ttu-id="85be4-201">Wenn auf die Baugruppe verwiesen wird, auf die die Komponente verweist, steht die Komponente zur Verwendung zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="85be4-201">If the assembly containing the component is referenced, then the component is available for use.</span></span> <span data-ttu-id="85be4-202">Um den Namespace der Komponente in `@using` den Anwendungsbereich zu bringen, wenden Sie die Direktive an:</span><span class="sxs-lookup"><span data-stu-id="85be4-202">To bring the component's namespace into scope, apply the `@using` directive:</span></span>

```razor
@using MyComponentLib

<Counter />
```

<span data-ttu-id="85be4-203">Wie in den standardmäßigen Blazor-Projekten gesehen, ist es üblich, Direktiven in eine `@using` *_Imports.razor-Datei* zu setzen, so dass sie in alle *.razor-Dateien* im selben Verzeichnis und in untergeordneten Verzeichnissen importiert werden.</span><span class="sxs-lookup"><span data-stu-id="85be4-203">As seen in the default Blazor projects, it's common to put `@using` directives into a *_Imports.razor* file so that they're imported into all *.razor* files in the same directory and in child directories.</span></span>

<span data-ttu-id="85be4-204">Wenn sich der Namespace für eine Komponente nicht im Gültigkeitsbereich befindet, können Sie eine Komponente mit ihrem vollständigen Typnamen angeben, wie Sie dies in C':</span><span class="sxs-lookup"><span data-stu-id="85be4-204">If the namespace for a component isn't in scope, you can specify a component using its full type name, as you can in C#:</span></span>

```razor
<MyComponentLib.Counter />
```

## <a name="component-parameters"></a><span data-ttu-id="85be4-205">Komponentenparameter</span><span class="sxs-lookup"><span data-stu-id="85be4-205">Component parameters</span></span>

<span data-ttu-id="85be4-206">In ASP.NET Web Forms können Sie Parameter und Daten mithilfe öffentlicher Eigenschaften an Steuerelemente weiterfließen lassen.</span><span class="sxs-lookup"><span data-stu-id="85be4-206">In ASP.NET Web Forms, you can flow parameters and data to controls using public properties.</span></span> <span data-ttu-id="85be4-207">Diese Eigenschaften können in Markup mithilfe von Attributen oder direkt im Code festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="85be4-207">These properties can be set in markup using attributes or set directly in code.</span></span> <span data-ttu-id="85be4-208">Blazor-Komponenten funktionieren auf ähnliche Weise, obwohl die Komponenteneigenschaften ebenfalls mit dem `[Parameter]` Attribut gekennzeichnet werden müssen, das als Komponentenparameter betrachtet werden soll.</span><span class="sxs-lookup"><span data-stu-id="85be4-208">Blazor components work in a similar fashion, although the component properties must also be marked with the `[Parameter]` attribute to be considered component parameters.</span></span>

<span data-ttu-id="85be4-209">Die `Counter` folgende Komponente definiert einen `IncrementAmount` Komponentenparameter namens, der verwendet `Counter` werden kann, um den Betrag anzugeben, der bei jedem Klicken auf die Schaltfläche erhöht werden soll.</span><span class="sxs-lookup"><span data-stu-id="85be4-209">The following `Counter` component defines a component parameter called `IncrementAmount` that can be used to specify the amount that the `Counter` should be incremented each time the button is clicked.</span></span>

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

<span data-ttu-id="85be4-210">Um einen Komponentenparameter in Blazor anzugeben, verwenden Sie ein Attribut wie in ASP.NET Web Forms:</span><span class="sxs-lookup"><span data-stu-id="85be4-210">To specify a component parameter in Blazor, use an attribute as you would in ASP.NET Web Forms:</span></span>

```razor
<Counter IncrementAmount="10" />
```

## <a name="event-handlers"></a><span data-ttu-id="85be4-211">Ereignishandler</span><span class="sxs-lookup"><span data-stu-id="85be4-211">Event handlers</span></span>

<span data-ttu-id="85be4-212">Sowohl ASP.NET Web Forms als auch Blazor bieten ein ereignisbasiertes Programmiermodell für die Behandlung von UI-Ereignissen.</span><span class="sxs-lookup"><span data-stu-id="85be4-212">Both ASP.NET Web Forms and Blazor provide an event-based programming model for handling UI events.</span></span> <span data-ttu-id="85be4-213">Beispiele für solche Ereignisse sind Schaltflächenklicks und Texteingabe.</span><span class="sxs-lookup"><span data-stu-id="85be4-213">Examples of such events include button clicks and text input.</span></span> <span data-ttu-id="85be4-214">In ASP.NET Web Forms verwenden Sie HTML-Serversteuerelemente, um UI-Ereignisse zu verarbeiten, die vom DOM verfügbar gemacht werden, oder Sie können Ereignisse verarbeiten, die von Webserversteuerelementen verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="85be4-214">In ASP.NET Web Forms, you use HTML server controls to handle UI events exposed by the DOM, or you can handle events exposed by web server controls.</span></span> <span data-ttu-id="85be4-215">Die Ereignisse werden auf dem Server über Formular-Post-Back-Anforderungen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="85be4-215">The events are surfaced on the server through form post-back requests.</span></span> <span data-ttu-id="85be4-216">Betrachten Sie die folgende Web Forms Schaltfläche klicken Beispiel:</span><span class="sxs-lookup"><span data-stu-id="85be4-216">Consider the following Web Forms button click example:</span></span>

<span data-ttu-id="85be4-217">*Counter.ascx*</span><span class="sxs-lookup"><span data-stu-id="85be4-217">*Counter.ascx*</span></span>

```aspx-csharp
<asp:Button ID="ClickMeButton" runat="server" Text="Click me!" OnClick="ClickMeButton_Click" />
```

<span data-ttu-id="85be4-218">*Counter.ascx.cs*</span><span class="sxs-lookup"><span data-stu-id="85be4-218">*Counter.ascx.cs*</span></span>

```csharp
public partial class Counter : System.Web.UI.UserControl
{
    protected void ClickMeButton_Click(object sender, EventArgs e)
    {
        Console.WriteLine("The button was clicked!");
    }
}
```

<span data-ttu-id="85be4-219">In Blazor können Sie Handler für DOM-UI-Ereignisse direkt `@on{event}`mithilfe von Direktivenattributen des Formulars registrieren.</span><span class="sxs-lookup"><span data-stu-id="85be4-219">In Blazor, you can register handlers for DOM UI events directly using directive attributes of the form `@on{event}`.</span></span> <span data-ttu-id="85be4-220">Der `{event}` Platzhalter stellt den Namen des Ereignisses dar.</span><span class="sxs-lookup"><span data-stu-id="85be4-220">The `{event}` placeholder represents the name of the event.</span></span> <span data-ttu-id="85be4-221">Sie können z. B. auf Schaltflächenklicks wie folgt hören:</span><span class="sxs-lookup"><span data-stu-id="85be4-221">For example, you can listen for button clicks like this:</span></span>

```razor
<button @onclick="OnClick">Click me!</button>

@code {
    void OnClick()
    {
        Console.WriteLine("The button was clicked!);
    }
}
```

<span data-ttu-id="85be4-222">Ereignishandler können ein optionales, ereignisspezifisches Argument akzeptieren, um weitere Informationen zum Ereignis bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="85be4-222">Event handlers can accept an optional, event-specific argument to provide more information about the event.</span></span> <span data-ttu-id="85be4-223">Mausereignisse können z. `MouseEventArgs` B. ein Argument annehmen, es ist jedoch nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="85be4-223">For example, mouse events can take a `MouseEventArgs` argument, but it isn't required.</span></span>

```razor
<button @onclick="OnClick">Click me!</button>

@code {
    void OnClick(MouseEventArgs e)
    {
        Console.WriteLine($"Mouse clicked at {e.ScreenX}, {e.ScreenY}.");
    }
}
```

<span data-ttu-id="85be4-224">Anstatt auf eine Methodengruppe für einen Ereignishandler zu verweisen, können Sie einen Lambda-Ausdruck verwenden.</span><span class="sxs-lookup"><span data-stu-id="85be4-224">Instead of referring to a method group for an event handler, you can use a lambda expression.</span></span> <span data-ttu-id="85be4-225">Mit einem Lambda-Ausdruck können Sie andere Werte im Gültigkeitsbereich schließen.</span><span class="sxs-lookup"><span data-stu-id="85be4-225">A lambda expression allows you to close over other in-scope values.</span></span>

```razor
@foreach (var buttonLabel in buttonLabels)
{
    <button @onclick="() => Console.WriteLine($"The {buttonLabel} button was clicked!")">@buttonLabel</button>
}
```

<span data-ttu-id="85be4-226">Ereignishandler können synchron oder asynchron ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="85be4-226">Event handlers can execute synchronously or asynchronously.</span></span> <span data-ttu-id="85be4-227">Der folgende `OnClick` Ereignishandler wird z. B. asynchron ausgeführt:</span><span class="sxs-lookup"><span data-stu-id="85be4-227">For example, the following `OnClick` event handler executes asynchronously:</span></span>

```razor
<button @onclick="OnClick">Click me!</button>

@code {
    async Task OnClick()
    {
        var result = await Http.GetAsync("api/values");
    }
}
```

<span data-ttu-id="85be4-228">Nachdem ein Ereignis behandelt wurde, wird die Komponente gerendert, um alle Komponentenstatusänderungen zu berücksichtigen.</span><span class="sxs-lookup"><span data-stu-id="85be4-228">After an event is handled, the component is rendered to account for any component state changes.</span></span> <span data-ttu-id="85be4-229">Bei asynchronen Ereignishandlern wird die Komponente unmittelbar nach Abschluss der Handlerausführung gerendert.</span><span class="sxs-lookup"><span data-stu-id="85be4-229">With asynchronous event handlers, the component is rendered immediately after the handler execution completes.</span></span> <span data-ttu-id="85be4-230">Die Komponente wird *nach* Abschluss der `Task` Asynchronität wieder gerendert.</span><span class="sxs-lookup"><span data-stu-id="85be4-230">The component is rendered *again* after the asynchronous `Task` completes.</span></span> <span data-ttu-id="85be4-231">Dieser asynchrone Ausführungsmodus bietet die Möglichkeit, eine `Task` geeignete Benutzeroberfläche zu rendern, während die asynchrone noch ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="85be4-231">This asynchronous execution mode provides an opportunity to render some appropriate UI while the asynchronous `Task` is still in progress.</span></span>

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

<span data-ttu-id="85be4-232">Komponenten können auch ihre eigenen Ereignisse definieren, `EventCallback<TValue>`indem sie einen Komponentenparameter vom Typ definieren.</span><span class="sxs-lookup"><span data-stu-id="85be4-232">Components can also define their own events by defining a component parameter of type `EventCallback<TValue>`.</span></span> <span data-ttu-id="85be4-233">Ereignisrückrufe unterstützen alle Variationen von DOM UI-Ereignishandlern: optionale Argumente, synchron ezielle oder asynchrone, Methodengruppen oder Lambda-Ausdrücke.</span><span class="sxs-lookup"><span data-stu-id="85be4-233">Event callbacks support all the variations of DOM UI event handlers: optional arguments, synchronous or asynchronous, method groups, or lambda expressions.</span></span>

```razor
<button class="btn btn-primary" @onclick="OnClick">Click me!</button>

@code {
    [Parameter]
    public EventCallback<MouseEventArgs> OnClick { get; set; }
}
```

## <a name="data-binding"></a><span data-ttu-id="85be4-234">Datenbindung</span><span class="sxs-lookup"><span data-stu-id="85be4-234">Data binding</span></span>

<span data-ttu-id="85be4-235">Blazor bietet einen einfachen Mechanismus zum Binden von Daten aus einer UI-Komponente an den Zustand der Komponente.</span><span class="sxs-lookup"><span data-stu-id="85be4-235">Blazor provides a simple mechanism to bind data from a UI component to the component's state.</span></span> <span data-ttu-id="85be4-236">Dieser Ansatz unterscheidet sich von den Features in ASP.NET Web Forms zum Binden von Daten aus Datenquellen an UI-Steuerelemente.</span><span class="sxs-lookup"><span data-stu-id="85be4-236">This approach differs from the features in ASP.NET Web Forms for binding data from data sources to UI controls.</span></span> <span data-ttu-id="85be4-237">Im Abschnitt [Umgang mit Daten](data.md) werden die Handhabung von Daten aus verschiedenen Datenquellen behandelt.</span><span class="sxs-lookup"><span data-stu-id="85be4-237">We'll cover handling data from different data sources in the [Dealing with data](data.md) section.</span></span>

<span data-ttu-id="85be4-238">Um eine bidirektionade Datenbindung von einer UI-Komponente in `@bind` den Zustand der Komponente zu erstellen, verwenden Sie das Direktive-Attribut.</span><span class="sxs-lookup"><span data-stu-id="85be4-238">To create a two-way data binding from a UI component to the component's state, use the `@bind` directive attribute.</span></span> <span data-ttu-id="85be4-239">Im folgenden Beispiel ist der Wert des Kontrollkästchens an das `isChecked` Feld gebunden.</span><span class="sxs-lookup"><span data-stu-id="85be4-239">In the following example, the value of the check box is bound to the `isChecked` field.</span></span>

```razor
<input type="checkbox" @bind="isChecked" />

@code {
    bool isChecked;
}
```

<span data-ttu-id="85be4-240">Wenn die Komponente gerendert wird, wird der Wert `isChecked` des Kontrollkästchens auf den Wert des Felds festgelegt.</span><span class="sxs-lookup"><span data-stu-id="85be4-240">When the component is rendered, the value of the checkbox is set to the value of the `isChecked` field.</span></span> <span data-ttu-id="85be4-241">Wenn der Benutzer das Kontrollkästchen umschaltet, wird `onchange` `isChecked` das Ereignis ausgelöst, und das Feld wird auf den neuen Wert festgelegt.</span><span class="sxs-lookup"><span data-stu-id="85be4-241">When the user toggles the checkbox, the `onchange` event is fired and the `isChecked` field is set to the new value.</span></span> <span data-ttu-id="85be4-242">Die `@bind` Syntax in diesem Fall entspricht dem folgenden Markup:</span><span class="sxs-lookup"><span data-stu-id="85be4-242">The `@bind` syntax in this case is equivalent to the following markup:</span></span>

```razor
<input value="@isChecked" @onchange="(UIChangeEventArgs e) => isChecked = e.Value" />
```

<span data-ttu-id="85be4-243">Um das für die Bindung verwendete `@bind:event` Ereignis zu ändern, verwenden Sie das Attribut.</span><span class="sxs-lookup"><span data-stu-id="85be4-243">To change the event used for the bind, use the `@bind:event` attribute.</span></span>

```razor
<input @bind="text" @bind:event="oninput" />
<p>@text</p>

@code {
    string text;
}
```

<span data-ttu-id="85be4-244">Komponenten können auch die Datenbindung an ihre Parameter unterstützen.</span><span class="sxs-lookup"><span data-stu-id="85be4-244">Components can also support data binding to their parameters.</span></span> <span data-ttu-id="85be4-245">Um Daten bindung, definieren Sie einen Ereignisrückrufparameter mit demselben Namen wie der bindbare Parameter.</span><span class="sxs-lookup"><span data-stu-id="85be4-245">To data bind, define an event callback parameter with the same name as the bindable parameter.</span></span> <span data-ttu-id="85be4-246">Das Suffix "Geändert" wird dem Namen hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="85be4-246">The "Changed" suffix is added to the name.</span></span>

<span data-ttu-id="85be4-247">*PasswordBox.razor*</span><span class="sxs-lookup"><span data-stu-id="85be4-247">*PasswordBox.razor*</span></span>

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

<span data-ttu-id="85be4-248">Um eine Datenbindung an ein zugrunde liegendes UI-Element zu verketten, legen `@bind` Sie den Wert fest, und behandeln Sie das Ereignis direkt im UI-Element, anstatt das Attribut zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="85be4-248">To chain a data binding to an underlying UI element, set the value and handle the event directly on the UI element instead of using the `@bind` attribute.</span></span>

<span data-ttu-id="85be4-249">Um eine Bindung an einen `@bind-{Parameter}` Komponentenparameter zu verwenden, verwenden Sie ein Attribut, um den Parameter anzugeben, an den Sie binden möchten.</span><span class="sxs-lookup"><span data-stu-id="85be4-249">To bind to a component parameter, use a `@bind-{Parameter}` attribute to specify the parameter to which you want to bind.</span></span>

```razor
<PasswordBox @bind-Password="password" />

@code {
    string password;
}
```

## <a name="state-changes"></a><span data-ttu-id="85be4-250">Zustandsänderungen</span><span class="sxs-lookup"><span data-stu-id="85be4-250">State changes</span></span>

<span data-ttu-id="85be4-251">Wenn sich der Status der Komponente außerhalb eines normalen UI-Ereignisses oder Ereignisrückrufs geändert hat, muss die Komponente manuell signalisieren, dass sie erneut gerendert werden muss.</span><span class="sxs-lookup"><span data-stu-id="85be4-251">If the component's state has changed outside of a normal UI event or event callback, then the component must manually signal that it needs to be rendered again.</span></span> <span data-ttu-id="85be4-252">Um zu signalisieren, dass sich der `StateHasChanged` Status einer Komponente geändert hat, rufen Sie die Methode für die Komponente auf.</span><span class="sxs-lookup"><span data-stu-id="85be4-252">To signal that a component's state has changed, call the `StateHasChanged` method on the component.</span></span>

<span data-ttu-id="85be4-253">Im folgenden Beispiel zeigt eine Komponente `AppState` eine Nachricht von einem Dienst an, die von anderen Teilen der App aktualisiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="85be4-253">In the example below, a component displays a message from an `AppState` service that can be updated by other parts of the app.</span></span> <span data-ttu-id="85be4-254">Die Komponente registriert `StateHasChanged` ihre `AppState.OnChange` Methode bei dem Ereignis, sodass die Komponente gerendert wird, wenn die Nachricht aktualisiert wird.</span><span class="sxs-lookup"><span data-stu-id="85be4-254">The component registers its `StateHasChanged` method with the `AppState.OnChange` event so that the component is rendered whenever the message gets updated.</span></span>

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

## <a name="component-lifecycle"></a><span data-ttu-id="85be4-255">Komponentenlebenszyklus</span><span class="sxs-lookup"><span data-stu-id="85be4-255">Component lifecycle</span></span>

<span data-ttu-id="85be4-256">Das ASP.NET Web Forms-Framework verfügt über klar definierte Lebenszyklusmethoden für Module, Seiten und Steuerelemente.</span><span class="sxs-lookup"><span data-stu-id="85be4-256">The ASP.NET Web Forms framework has well-defined lifecycle methods for modules, pages, and controls.</span></span> <span data-ttu-id="85be4-257">Das folgende Steuerelement implementiert beispielsweise Ereignishandler `Init`für `Load`die `UnLoad` Ereignisse , und Lifecycle:</span><span class="sxs-lookup"><span data-stu-id="85be4-257">For example, the following control implements event handlers for the `Init`, `Load`, and `UnLoad` lifecycle events:</span></span>

<span data-ttu-id="85be4-258">*Counter.ascx.cs*</span><span class="sxs-lookup"><span data-stu-id="85be4-258">*Counter.ascx.cs*</span></span>

```csharp
public partial class Counter : System.Web.UI.UserControl
{
    protected void Page_Init(object sender, EventArgs e) { ... }
    protected void Page_Load(object sender, EventArgs e) { ... }
    protected void Page_UnLoad(object sender, EventArgs e) { ... }
}
```

<span data-ttu-id="85be4-259">Blazor-Komponenten haben auch einen genau definierten Lebenszyklus.</span><span class="sxs-lookup"><span data-stu-id="85be4-259">Blazor components also have a well-defined lifecycle.</span></span> <span data-ttu-id="85be4-260">Der Lebenszyklus einer Komponente kann verwendet werden, um den Komponentenstatus zu initialisieren und erweitertes Komponentenverhalten zu implementieren.</span><span class="sxs-lookup"><span data-stu-id="85be4-260">A component's lifecycle can be used to initialize component state and implement advanced component behaviors.</span></span>

<span data-ttu-id="85be4-261">Alle Komponentenlebenszyklusmethoden von Blazor verfügen sowohl über synchrone als auch über asynchrone Versionen.</span><span class="sxs-lookup"><span data-stu-id="85be4-261">All of Blazor's component lifecycle methods have both synchronous and asynchronous versions.</span></span> <span data-ttu-id="85be4-262">Das Komponentenrendering ist synchron.</span><span class="sxs-lookup"><span data-stu-id="85be4-262">Component rendering is synchronous.</span></span> <span data-ttu-id="85be4-263">Sie können keine asynchrone Logik als Teil des Komponentenrenderings ausführen.</span><span class="sxs-lookup"><span data-stu-id="85be4-263">You can't run asynchronous logic as part of the component rendering.</span></span> <span data-ttu-id="85be4-264">Alle asynchronen Logiken müssen `async` als Teil einer Lebenszyklusmethode ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="85be4-264">All asynchronous logic must execute as part of an `async` lifecycle method.</span></span>

### <a name="oninitialized"></a><span data-ttu-id="85be4-265">Oninitialized</span><span class="sxs-lookup"><span data-stu-id="85be4-265">OnInitialized</span></span>

<span data-ttu-id="85be4-266">Die `OnInitialized` `OnInitializedAsync` und Methoden werden verwendet, um die Komponente zu initialisieren.</span><span class="sxs-lookup"><span data-stu-id="85be4-266">The `OnInitialized` and `OnInitializedAsync` methods are used to initialize the component.</span></span> <span data-ttu-id="85be4-267">Eine Komponente wird in der Regel initialisiert, nachdem sie zum ersten Mal gerendert wurde.</span><span class="sxs-lookup"><span data-stu-id="85be4-267">A component is typically initialized after it's first rendered.</span></span> <span data-ttu-id="85be4-268">Nachdem eine Komponente initialisiert wurde, kann sie mehrmals gerendert werden, bevor sie schließlich verworfen wird.</span><span class="sxs-lookup"><span data-stu-id="85be4-268">After a component is initialized, it may be rendered multiple times before it's eventually disposed.</span></span> <span data-ttu-id="85be4-269">Die `OnInitialized` Methode ähnelt `Page_Load` dem Ereignis in ASP.NET Web Forms-Seiten und -Steuerelementen.</span><span class="sxs-lookup"><span data-stu-id="85be4-269">The `OnInitialized` method is similar to the `Page_Load` event in ASP.NET Web Forms pages and controls.</span></span>

```csharp
protected override void OnInitialized() { ... }
protected override async Task OnInitializedAsync() { await ... }
```

### <a name="onparametersset"></a><span data-ttu-id="85be4-270">OnParametersSet</span><span class="sxs-lookup"><span data-stu-id="85be4-270">OnParametersSet</span></span>

<span data-ttu-id="85be4-271">Die `OnParametersSet` `OnParametersSetAsync` und-Methoden werden aufgerufen, wenn eine Komponente Parameter von ihrem übergeordneten Element empfangen hat und der Wert Eigenschaften zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="85be4-271">The `OnParametersSet` and `OnParametersSetAsync` methods are called when a component has received parameters from its parent and the value are assigned to properties.</span></span> <span data-ttu-id="85be4-272">Diese Methoden werden nach der Komponenteninitialisierung und *bei jeder Gerederung der Komponente*ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="85be4-272">These methods are executed after component initialization and *each time the component is rendered*.</span></span>

```csharp
protected override void OnParametersSet() { ... }
protected override async Task OnParametersSetAsync() { await ... }
```

### <a name="onafterrender"></a><span data-ttu-id="85be4-273">OnAfterRender</span><span class="sxs-lookup"><span data-stu-id="85be4-273">OnAfterRender</span></span>

<span data-ttu-id="85be4-274">Die `OnAfterRender` `OnAfterRenderAsync` und-Methoden werden aufgerufen, nachdem eine Komponente das Rendern abgeschlossen hat.</span><span class="sxs-lookup"><span data-stu-id="85be4-274">The `OnAfterRender` and `OnAfterRenderAsync` methods are called after a component has finished rendering.</span></span> <span data-ttu-id="85be4-275">Element- und Komponentenreferenzen werden an dieser Stelle aufgefüllt (mehr zu diesen Konzepten unten).</span><span class="sxs-lookup"><span data-stu-id="85be4-275">Element and component references are populated at this point (more on these concepts below).</span></span> <span data-ttu-id="85be4-276">Die Interaktivität mit dem Browser ist an dieser Stelle aktiviert.</span><span class="sxs-lookup"><span data-stu-id="85be4-276">Interactivity with the browser is enabled at this point.</span></span> <span data-ttu-id="85be4-277">Interaktionen mit der DOM- und JavaScript-Ausführung können sicher stattfinden.</span><span class="sxs-lookup"><span data-stu-id="85be4-277">Interactions with the DOM and JavaScript execution can safely take place.</span></span>

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

<span data-ttu-id="85be4-278">`OnAfterRender`und `OnAfterRenderAsync` *werden beim Vorrendern auf dem Server nicht aufgerufen.*</span><span class="sxs-lookup"><span data-stu-id="85be4-278">`OnAfterRender` and `OnAfterRenderAsync` *aren't called when prerendering on the server*.</span></span>

<span data-ttu-id="85be4-279">Der `firstRender` Parameter `true` ist das erste Mal, dass die Komponente gerendert wird. Andernfalls ist `false`sein Wert .</span><span class="sxs-lookup"><span data-stu-id="85be4-279">The `firstRender` parameter is `true` the first time the component is rendered; otherwise, its value is `false`.</span></span>

### <a name="idisposable"></a><span data-ttu-id="85be4-280">IDisposable</span><span class="sxs-lookup"><span data-stu-id="85be4-280">IDisposable</span></span>

<span data-ttu-id="85be4-281">Blazor-Komponenten `IDisposable` können implementiert werden, um Ressourcen zu entsorgen, wenn die Komponente aus der Benutzeroberfläche entfernt wird.</span><span class="sxs-lookup"><span data-stu-id="85be4-281">Blazor components can implement `IDisposable` to dispose of resources when the component is removed from the UI.</span></span> <span data-ttu-id="85be4-282">Eine Razor-Komponente `IDispose` kann `@implements` mithilfe der Direktive implementiert werden:</span><span class="sxs-lookup"><span data-stu-id="85be4-282">A Razor component can implement `IDispose` by using the `@implements` directive:</span></span>

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

## <a name="capture-component-references"></a><span data-ttu-id="85be4-283">Capture-Komponentenreferenzen</span><span class="sxs-lookup"><span data-stu-id="85be4-283">Capture component references</span></span>

<span data-ttu-id="85be4-284">In ASP.NET Web Forms ist es üblich, eine Steuerelementinstanz direkt im Code zu bearbeiten, indem auf ihre ID verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="85be4-284">In ASP.NET Web Forms, it's common to manipulate a control instance directly in code by referring to its ID.</span></span> <span data-ttu-id="85be4-285">In Blazor ist es auch möglich, einen Verweis auf eine Komponente zu erfassen und zu manipulieren, obwohl er viel seltener ist.</span><span class="sxs-lookup"><span data-stu-id="85be4-285">In Blazor, it's also possible to capture and manipulate a reference to a component, although it's much less common.</span></span>

<span data-ttu-id="85be4-286">Um einen Komponentenverweis in Blazor `@ref` zu erfassen, verwenden Sie das Direktive-Attribut.</span><span class="sxs-lookup"><span data-stu-id="85be4-286">To capture a component reference in Blazor, use the `@ref` directive attribute.</span></span> <span data-ttu-id="85be4-287">Der Wert des Attributs sollte mit dem Namen eines festsetzbaren Felds mit demselben Typ wie die referenzierte Komponente übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="85be4-287">The value of the attribute should match the name of a settable field with the same type as the referenced component.</span></span>

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

<span data-ttu-id="85be4-288">Wenn die übergeordnete Komponente gerendert wird, wird das Feld mit der untergeordneten Komponenteninstanz aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="85be4-288">When the parent component is rendered, the field is populated with the child component instance.</span></span> <span data-ttu-id="85be4-289">Anschließend können Sie Methoden auf der Komponenteninstanz aufrufen oder anderweitig bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="85be4-289">You can then call methods on, or otherwise manipulate, the component instance.</span></span>

<span data-ttu-id="85be4-290">Das Bearbeiten des Komponentenstatus direkt mithilfe von Komponentenreferenzen wird nicht empfohlen.</span><span class="sxs-lookup"><span data-stu-id="85be4-290">Manipulating component state directly using component references isn't recommended.</span></span> <span data-ttu-id="85be4-291">Dadurch wird verhindert, dass die Komponente automatisch zum richtigen Zeitpunkt gerendert wird.</span><span class="sxs-lookup"><span data-stu-id="85be4-291">Doing so prevents the component from being rendered automatically at the correct times.</span></span>

## <a name="capture-element-references"></a><span data-ttu-id="85be4-292">Erfassen von Elementreferenzen</span><span class="sxs-lookup"><span data-stu-id="85be4-292">Capture element references</span></span>

<span data-ttu-id="85be4-293">Blazor-Komponenten können Verweise auf ein Element erfassen.</span><span class="sxs-lookup"><span data-stu-id="85be4-293">Blazor components can capture references to an element.</span></span> <span data-ttu-id="85be4-294">Im Gegensatz zu HTML-Serversteuerelementen in ASP.NET Web Forms können Sie das DOM nicht direkt mithilfe eines Elementverweises in Blazor bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="85be4-294">Unlike HTML server controls in ASP.NET Web Forms, you can't manipulate the DOM directly using an element reference in Blazor.</span></span> <span data-ttu-id="85be4-295">Blazor verarbeitet die meisten DOM-Interaktionen für Sie mit seinem DOM-Diffing-Algorithmus.</span><span class="sxs-lookup"><span data-stu-id="85be4-295">Blazor handles most DOM interactions for you using its DOM diffing algorithm.</span></span> <span data-ttu-id="85be4-296">Erfasste Elementverweise in Blazor sind undurchsichtig.</span><span class="sxs-lookup"><span data-stu-id="85be4-296">Captured element references in Blazor are opaque.</span></span> <span data-ttu-id="85be4-297">Sie werden jedoch verwendet, um einen bestimmten Elementverweis in einem JavaScript-Interopaufruf zu übergeben.</span><span class="sxs-lookup"><span data-stu-id="85be4-297">However, they're used to pass a specific element reference in a JavaScript interop call.</span></span> <span data-ttu-id="85be4-298">Weitere Informationen zu JavaScript-Interop finden Sie [unter ASP.NET Core Blazor JavaScript interop](/aspnet/core/blazor/javascript-interop).</span><span class="sxs-lookup"><span data-stu-id="85be4-298">For more information about JavaScript interop, see [ASP.NET Core Blazor JavaScript interop](/aspnet/core/blazor/javascript-interop).</span></span>

## <a name="templated-components"></a><span data-ttu-id="85be4-299">Komponenten mit Vorlagen</span><span class="sxs-lookup"><span data-stu-id="85be4-299">Templated components</span></span>

<span data-ttu-id="85be4-300">In ASP.NET Web Forms können Sie *Vorlagensteuerelemente*erstellen.</span><span class="sxs-lookup"><span data-stu-id="85be4-300">In ASP.NET Web Forms, you can create *templated controls*.</span></span> <span data-ttu-id="85be4-301">Vorlagensteuerelemente ermöglichen es dem Entwickler, einen Teil des HTML-Codes anzugeben, der zum Rendern eines Containersteuerelements verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="85be4-301">Templated controls enable the developer to specify a portion of the HTML used to render a container control.</span></span> <span data-ttu-id="85be4-302">Die Mechanismen zum Erstellen von Serversteuerelementen mit Vorlagen sind komplex, ermöglichen jedoch leistungsstarke Szenarien zum benutzerdefinierten Rendern von Daten.</span><span class="sxs-lookup"><span data-stu-id="85be4-302">The mechanics of building templated server controls are complex, but they enable powerful scenarios for rendering data in a user customizable way.</span></span> <span data-ttu-id="85be4-303">Beispiele für Vorlagensteuerelemente sind `Repeater` und `DataList`.</span><span class="sxs-lookup"><span data-stu-id="85be4-303">Examples of templated controls include `Repeater` and `DataList`.</span></span>

<span data-ttu-id="85be4-304">Blazor-Komponenten können auch vorlagen, indem `RenderFragment` Komponentenparameter vom Typ oder `RenderFragment<T>`definiert werden.</span><span class="sxs-lookup"><span data-stu-id="85be4-304">Blazor components can also be templated by defining component parameters of type `RenderFragment` or `RenderFragment<T>`.</span></span> <span data-ttu-id="85be4-305">A `RenderFragment` stellt einen Teil des Razor-Markups dar, das dann von der Komponente gerendert werden kann.</span><span class="sxs-lookup"><span data-stu-id="85be4-305">A `RenderFragment` represents a chunk of Razor markup that can then be rendered by the component.</span></span> <span data-ttu-id="85be4-306">A `RenderFragment<T>` ist ein Teil des Razor-Markups, das einen Parameter annimmt, der angegeben werden kann, wenn das Renderfragment gerendert wird.</span><span class="sxs-lookup"><span data-stu-id="85be4-306">A `RenderFragment<T>` is a chunk of Razor markup that takes a parameter that can be specified when the render fragment is rendered.</span></span>

### <a name="child-content"></a><span data-ttu-id="85be4-307">Kinderinhalte</span><span class="sxs-lookup"><span data-stu-id="85be4-307">Child content</span></span>

<span data-ttu-id="85be4-308">Blazor-Komponenten können ihren untergeordneten Inhalt als untergeordneten `RenderFragment` Inhalt erfassen und diesen Inhalt als Teil des Komponentenrenderings rendern.</span><span class="sxs-lookup"><span data-stu-id="85be4-308">Blazor components can capture their child content as a `RenderFragment` and render that content as part of the component rendering.</span></span> <span data-ttu-id="85be4-309">Um untergeordnete nädenlegenden Inhalt `RenderFragment` zu `ChildContent`erfassen, definieren Sie einen Komponentenparameter des Typs, und benennen Sie ihn .</span><span class="sxs-lookup"><span data-stu-id="85be4-309">To capture child content, define a component parameter of type `RenderFragment` and name it `ChildContent`.</span></span>

<span data-ttu-id="85be4-310">*ChildContentComponent.razor*</span><span class="sxs-lookup"><span data-stu-id="85be4-310">*ChildContentComponent.razor*</span></span>

```razor
<h1>Component with child content</h1>

<div>@ChildContent</div>

@code {
    [Parameter]
    public RenderFragment ChildContent { get; set; }
}
```

<span data-ttu-id="85be4-311">Eine übergeordnete Komponente kann dann untergeordneten Inhalt mithilfe der normalen Razor-Syntax bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="85be4-311">A parent component can then supply child content using normal Razor syntax.</span></span>

```razor
<ChildContentComponent>
    <p>The time is @DateTime.Now</p>
</ChildContentComponent>
```

### <a name="template-parameters"></a><span data-ttu-id="85be4-312">Vorlagenparameter</span><span class="sxs-lookup"><span data-stu-id="85be4-312">Template parameters</span></span>

<span data-ttu-id="85be4-313">Eine Blazor-Komponente mit Vorlagen kann auch `RenderFragment` `RenderFragment<T>`mehrere Komponentenparameter vom Typ oder definieren.</span><span class="sxs-lookup"><span data-stu-id="85be4-313">A templated Blazor component can also define multiple component parameters of type `RenderFragment` or `RenderFragment<T>`.</span></span> <span data-ttu-id="85be4-314">Der Parameter `RenderFragment<T>` für a kann angegeben werden, wenn er aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="85be4-314">The parameter for a `RenderFragment<T>` can be specified when it's invoked.</span></span> <span data-ttu-id="85be4-315">Um einen generischen Typparameter für `@typeparam` eine Komponente anzugeben, verwenden Sie die Razor-Direktive.</span><span class="sxs-lookup"><span data-stu-id="85be4-315">To specify a generic type parameter for a component, use the `@typeparam` Razor directive.</span></span>

<span data-ttu-id="85be4-316">*SimpleListView.razor*</span><span class="sxs-lookup"><span data-stu-id="85be4-316">*SimpleListView.razor*</span></span>

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

<span data-ttu-id="85be4-317">Bei Verwendung einer Vorlagenkomponente können die Vorlagenparameter mithilfe untergeordneter Elemente angegeben werden, die den Namen der Parameter entsprechen.</span><span class="sxs-lookup"><span data-stu-id="85be4-317">When using a templated component, the template parameters can be specified using child elements that match the names of the parameters.</span></span> <span data-ttu-id="85be4-318">Komponentenargumente vom `RenderFragment<T>` Typ, der als `context`Elemente übergeben wird, haben einen impliziten Parameter mit dem Namen .</span><span class="sxs-lookup"><span data-stu-id="85be4-318">Component arguments of type `RenderFragment<T>` passed as elements have an implicit parameter named `context`.</span></span> <span data-ttu-id="85be4-319">Sie können den Namen dieses Implement-Parameters mithilfe des `Context` Attributs für das untergeordnete Element ändern.</span><span class="sxs-lookup"><span data-stu-id="85be4-319">You can change the name of this implement parameter using the `Context` attribute on the child element.</span></span> <span data-ttu-id="85be4-320">Alle generischen Typparameter können mithilfe eines Attributs angegeben werden, das mit dem Namen des Typparameters übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="85be4-320">Any generic type parameters can be specified using an attribute that matches the name of the type parameter.</span></span> <span data-ttu-id="85be4-321">Der Typparameter wird nach Möglichkeit abgeleitet:</span><span class="sxs-lookup"><span data-stu-id="85be4-321">The type parameter will be inferred if possible:</span></span>

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

<span data-ttu-id="85be4-322">Die Ausgabe dieser Komponente sieht wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="85be4-322">The output of this component looks like this:</span></span>

```html
<h1>My list</h1>
<ul>
    <li>The message is: message1</li>
    <li>The message is: message2</li>
<ul>
```

## <a name="code-behind"></a><span data-ttu-id="85be4-323">CodeBehind</span><span class="sxs-lookup"><span data-stu-id="85be4-323">Code-behind</span></span>

<span data-ttu-id="85be4-324">Eine Blazor-Komponente wird in der Regel in einer einzelnen *.razor-Datei* erstellt.</span><span class="sxs-lookup"><span data-stu-id="85be4-324">A Blazor component is typically authored in a single *.razor* file.</span></span> <span data-ttu-id="85be4-325">Es ist jedoch auch möglich, Code und Markup mithilfe einer CodeBehind-Datei zu trennen.</span><span class="sxs-lookup"><span data-stu-id="85be4-325">However, it's also possible to separate the code and markup using a code-behind file.</span></span> <span data-ttu-id="85be4-326">Um eine Komponentendatei zu verwenden, fügen Sie eine C-Datei hinzu, die mit dem Dateinamen der Komponentendatei übereinstimmt, jedoch mit einer *hinzugefügten .cs-Erweiterung* (*Counter.razor.cs*hinzugefügt wurde).</span><span class="sxs-lookup"><span data-stu-id="85be4-326">To use a component file, add a C# file that matches the file name of the component file but with a *.cs* extension added (*Counter.razor.cs*).</span></span> <span data-ttu-id="85be4-327">Verwenden Sie die C-Datei, um eine Basisklasse für die Komponente zu definieren.</span><span class="sxs-lookup"><span data-stu-id="85be4-327">Use the C# file to define a base class for the component.</span></span> <span data-ttu-id="85be4-328">Sie können die Basisklasse nach Bekunden benennen, aber es ist üblich, die Klasse wie `Base` die`CounterBase`Komponentenklasse zu benennen, jedoch mit einer zusätzlichen Erweiterung ( ).</span><span class="sxs-lookup"><span data-stu-id="85be4-328">You can name the base class anything you'd like, but it's common to name the class the same as the component class, but with a `Base` extension added (`CounterBase`).</span></span> <span data-ttu-id="85be4-329">Die komponentenbasierte Klasse muss ebenfalls `ComponentBase`von stammen.</span><span class="sxs-lookup"><span data-stu-id="85be4-329">The component-based class must also derive from `ComponentBase`.</span></span> <span data-ttu-id="85be4-330">Fügen Sie dann in der `@inherits` Razor-Komponentendatei die Direktive`@inherits CounterBase`hinzu, um die Basisklasse für die Komponente ( anzugeben).</span><span class="sxs-lookup"><span data-stu-id="85be4-330">Then, in the Razor component file, add the `@inherits` directive to specify the base class for the component (`@inherits CounterBase`).</span></span>

<span data-ttu-id="85be4-331">*Counter.razor*</span><span class="sxs-lookup"><span data-stu-id="85be4-331">*Counter.razor*</span></span>

```razor
@inherits CounterBase

<h1>Counter</h1>

<p>Current count: @currentCount</p>

<button @onclick="IncrementCount">Click me</button>
```

<span data-ttu-id="85be4-332">*Counter.razor.cs*</span><span class="sxs-lookup"><span data-stu-id="85be4-332">*Counter.razor.cs*</span></span>

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

<span data-ttu-id="85be4-333">Die Sichtbarkeit der Komponentenmember in der Basisklasse muss für die Komponentenklasse sichtbar sein `protected` oder `public` sichtbar sein.</span><span class="sxs-lookup"><span data-stu-id="85be4-333">The visibility of the component's members in the base class must be `protected` or `public` to be visible to the component class.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="85be4-334">Zusätzliche Ressourcen</span><span class="sxs-lookup"><span data-stu-id="85be4-334">Additional resources</span></span>

<span data-ttu-id="85be4-335">Die vorhergehende ist nicht eine erschöpfende Behandlung aller Aspekte von Blazor Komponenten.</span><span class="sxs-lookup"><span data-stu-id="85be4-335">The preceding isn't an exhaustive treatment of all aspects of Blazor components.</span></span> <span data-ttu-id="85be4-336">Weitere Informationen zum [Erstellen und Verwenden ASP.NET Core Razor-Komponenten](/aspnet/core/blazor/components)finden Sie in der Blazor-Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="85be4-336">For more information on how to [Create and use ASP.NET Core Razor components](/aspnet/core/blazor/components), see the Blazor documentation.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="85be4-337">[VorherigeS](app-startup.md)
>[Weiter](pages-routing-layouts.md)</span><span class="sxs-lookup"><span data-stu-id="85be4-337">[Previous](app-startup.md)
[Next](pages-routing-layouts.md)</span></span>
