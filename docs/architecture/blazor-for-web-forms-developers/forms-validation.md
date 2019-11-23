---
title: Formulare und Überprüfung
description: Erfahren Sie, wie Sie Formulare mit Client seitiger Validierung in blazor erstellen.
author: danroth27
ms.author: daroth
ms.date: 09/19/2019
ms.openlocfilehash: c30db5e06d36a6d15301835fe782b21058a80592
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73841954"
---
# <a name="forms-and-validation"></a><span data-ttu-id="328cb-103">Formulare und Überprüfung</span><span class="sxs-lookup"><span data-stu-id="328cb-103">Forms and validation</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="328cb-104">Das ASP.net Web Forms Framework enthält eine Reihe von Validierungsserver Steuerelementen, die das Validieren der in ein Formular eingegebenen Benutzereingaben (`RequiredFieldValidator`, `CompareValidator`, `RangeValidator`usw.) behandeln.</span><span class="sxs-lookup"><span data-stu-id="328cb-104">The ASP.NET Web Forms framework includes a set of validation server controls that handle validating user input entered into a form (`RequiredFieldValidator`, `CompareValidator`, `RangeValidator`, and so on).</span></span> <span data-ttu-id="328cb-105">Das ASP.net Web Forms Framework unterstützt auch die Modell Bindung und die Validierung des Modells auf der Grundlage von Daten Anmerkungen (`[Required]`, `[StringLength]`, `[Range]`usw.).</span><span class="sxs-lookup"><span data-stu-id="328cb-105">The ASP.NET Web Forms framework also supports model binding and validating the model based on data annotations (`[Required]`, `[StringLength]`, `[Range]`, and so on).</span></span> <span data-ttu-id="328cb-106">Die Validierungs Logik kann sowohl auf dem Server als auch auf dem Client mithilfe unaufdringlicher JavaScript-basierter Validierung erzwungen werden.</span><span class="sxs-lookup"><span data-stu-id="328cb-106">The validation logic can be enforced both on the server and on the client using unobtrusive JavaScript-based validation.</span></span> <span data-ttu-id="328cb-107">Das `ValidationSummary` Server-Steuerelement wird verwendet, um eine Zusammenfassung der Validierungs Fehler für den Benutzer anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="328cb-107">The `ValidationSummary` server control is used to display a summary of the validation errors to the user.</span></span>

<span data-ttu-id="328cb-108">Blazor unterstützt die Freigabe der Validierungs Logik zwischen dem Client und dem Server.</span><span class="sxs-lookup"><span data-stu-id="328cb-108">Blazor supports the sharing of validation logic between both the client and the server.</span></span> <span data-ttu-id="328cb-109">ASP.net bietet vorgefertigte JavaScript-Implementierungen vieler allgemeiner Server Überprüfungen.</span><span class="sxs-lookup"><span data-stu-id="328cb-109">ASP.NET provides pre-built JavaScript implementations of many common server validations.</span></span> <span data-ttu-id="328cb-110">In vielen Fällen muss der Entwickler trotzdem JavaScript schreiben, um seine App-spezifische Validierungs Logik vollständig zu implementieren.</span><span class="sxs-lookup"><span data-stu-id="328cb-110">In many cases, the developer still has to write JavaScript to fully implement their app-specific validation logic.</span></span> <span data-ttu-id="328cb-111">Die gleichen Modelltypen, Daten Anmerkungen und Validierungs Logik können sowohl auf dem Server als auch auf dem Client verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="328cb-111">The same model types, data annotations, and validation logic can be used on both the server and client.</span></span>

<span data-ttu-id="328cb-112">Blazor stellt eine Reihe von Eingabe Komponenten bereit.</span><span class="sxs-lookup"><span data-stu-id="328cb-112">Blazor provides a set of input components.</span></span> <span data-ttu-id="328cb-113">Die Eingabe Komponenten behandeln die Bindungs Felddaten an ein Modell und validieren die Benutzereingaben, wenn das Formular übermittelt wird.</span><span class="sxs-lookup"><span data-stu-id="328cb-113">The input components handle binding field data to a model and validating the user input when the form is submitted.</span></span>

|<span data-ttu-id="328cb-114">Eingabe Komponente</span><span class="sxs-lookup"><span data-stu-id="328cb-114">Input component</span></span>|<span data-ttu-id="328cb-115">Gerendertes Element HTML</span><span class="sxs-lookup"><span data-stu-id="328cb-115">Rendered HTML element</span></span>    |
|---------------|-------------------------|
|`InputCheckbox`|`<input type="checkbox">`|
|`InputDate`    |`<input type="date">`    |
|`InputNumber`  |`<input type="number">`  |
|`InputSelect`  |`<select>`               |
|`InputText`    |`<input>`                |
|`InputTextArea`|`<textarea>`             |

<span data-ttu-id="328cb-116">Die `EditForm` Komponente umschließt diese Eingabe Komponenten und orchestriert den Validierungsprozess über einen `EditContext`.</span><span class="sxs-lookup"><span data-stu-id="328cb-116">The `EditForm` component wraps these input components and orchestrates the validation process through an `EditContext`.</span></span> <span data-ttu-id="328cb-117">Wenn Sie einen `EditForm`erstellen, geben Sie an, welche Modell Instanz mithilfe des `Model`-Parameters gebunden werden soll.</span><span class="sxs-lookup"><span data-stu-id="328cb-117">When creating an `EditForm`, you specify what model instance to bind to using the `Model` parameter.</span></span> <span data-ttu-id="328cb-118">Die Validierung erfolgt in der Regel mithilfe von Daten Anmerkungen und ist erweiterbar.</span><span class="sxs-lookup"><span data-stu-id="328cb-118">Validation is typically done using data annotations, and it's extensible.</span></span> <span data-ttu-id="328cb-119">Fügen Sie zum Aktivieren der Überprüfung auf Daten Anmerkungen die `DataAnnotationsValidator` Komponente als untergeordnetes Element des `EditForm`hinzu.</span><span class="sxs-lookup"><span data-stu-id="328cb-119">To enable data annotation-based validation, add the `DataAnnotationsValidator` component as a child of the `EditForm`.</span></span> <span data-ttu-id="328cb-120">Die `EditForm` Komponente bietet ein nützliches Ereignis für die Behandlung gültiger (`OnValidSubmit`) und Ungültiger (`OnInvalidSubmit`) Übermittlungen.</span><span class="sxs-lookup"><span data-stu-id="328cb-120">The `EditForm` component provides a convenient event for handling valid (`OnValidSubmit`) and invalid (`OnInvalidSubmit`) submissions.</span></span> <span data-ttu-id="328cb-121">Außerdem gibt es ein allgemeineres `OnSubmit` Ereignis, mit dem Sie die Überprüfung selbst auslösen und behandeln können.</span><span class="sxs-lookup"><span data-stu-id="328cb-121">There's also a more generic `OnSubmit` event that lets you trigger and handle the validation yourself.</span></span>

<span data-ttu-id="328cb-122">Um eine Zusammenfassung der Überprüfungs Fehler anzuzeigen, verwenden Sie die `ValidationSummary` Komponente.</span><span class="sxs-lookup"><span data-stu-id="328cb-122">To display a validation error summary, use the `ValidationSummary` component.</span></span> <span data-ttu-id="328cb-123">Verwenden Sie zum Anzeigen von Validierungs Meldungen für ein bestimmtes Eingabefeld die `ValidationMessage` Komponente, und geben Sie einen Lambda-Ausdruck für den `For` Parameter an, der auf das entsprechende Modellelement zeigt.</span><span class="sxs-lookup"><span data-stu-id="328cb-123">To display validation messages for a specific input field, use the `ValidationMessage` component, specifying a lambda expression for the `For` parameter that points to the appropriate model member.</span></span>

<span data-ttu-id="328cb-124">Der folgende Modelltyp definiert mehrere Validierungsregeln mithilfe von Daten Anmerkungen:</span><span class="sxs-lookup"><span data-stu-id="328cb-124">The following model type defines several validation rules using data annotations:</span></span>

```csharp
using System;
using System.ComponentModel.DataAnnotations;

public class Starship
{
    [Required]
    [StringLength(16,
        ErrorMessage = "Identifier too long (16 character limit).")]
    public string Identifier { get; set; }

    public string Description { get; set; }

    [Required]
    public string Classification { get; set; }

    [Range(1, 100000,
        ErrorMessage = "Accommodation invalid (1-100000).")]
    public int MaximumAccommodation { get; set; }

    [Required]
    [Range(typeof(bool), "true", "true",
        ErrorMessage = "This form disallows unapproved ships.")]
    public bool IsValidatedDesign { get; set; }

    [Required]
    public DateTime ProductionDate { get; set; }
}
```

<span data-ttu-id="328cb-125">Die folgende Komponente veranschaulicht das Erstellen eines Formulars in blazor basierend auf dem `Starship` Modelltyp:</span><span class="sxs-lookup"><span data-stu-id="328cb-125">The following component demonstrates building a form in Blazor based on the `Starship` model type:</span></span>

```razor
<h1>New Ship Entry Form</h1>

<EditForm Model="@starship" OnValidSubmit="@HandleValidSubmit">
    <DataAnnotationsValidator />
    <ValidationSummary />

    <p>
        <label for="identifier">Identifier: </label>
        <InputText id="identifier" @bind-Value="starship.Identifier" />
        <ValidationMessage For="() => starship.Identifier" />
    </p>
    <p>
        <label for="description">Description (optional): </label>
        <InputTextArea id="description" @bind-Value="starship.Description" />
    </p>
    <p>
        <label for="classification">Primary Classification: </label>
        <InputSelect id="classification" @bind-Value="starship.Classification">
            <option value="">Select classification ...</option>
            <option value="Exploration">Exploration</option>
            <option value="Diplomacy">Diplomacy</option>
            <option value="Defense">Defense</option>
        </InputSelect>
        <ValidationMessage For="() => starship.Classification" />
    </p>
    <p>
        <label for="accommodation">Maximum Accommodation: </label>
        <InputNumber id="accommodation" @bind-Value="starship.MaximumAccommodation" />
        <ValidationMessage For="() => starship.MaximumAccommodation" />
    </p>
    <p>
        <label for="valid">Engineering Approval: </label>
        <InputCheckbox id="valid" @bind-Value="starship.IsValidatedDesign" />
        <ValidationMessage For="() => starship.IsValidatedDesign" />
    </p>
    <p>
        <label for="productionDate">Production Date: </label>
        <InputDate id="productionDate" @bind-Value="starship.ProductionDate" />
        <ValidationMessage For="() => starship.ProductionDate" />
    </p>

    <button type="submit">Submit</button>
</EditForm>

@code {
    private Starship starship = new Starship();

    private void HandleValidSubmit()
    {
        // Save the data
    }
}
```

<span data-ttu-id="328cb-126">Nach der Übermittlung des Formulars wurden die Modell gebundenen Daten nicht in einem Datenspeicher gespeichert, wie z. b. einer Datenbank.</span><span class="sxs-lookup"><span data-stu-id="328cb-126">After the form submission, the model-bound data hasn't been saved to any data store, like a database.</span></span> <span data-ttu-id="328cb-127">In einer blazor Webassembly-App müssen die Daten an den Server gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="328cb-127">In a Blazor WebAssembly app, the data must be sent to the server.</span></span> <span data-ttu-id="328cb-128">Beispielsweise mithilfe einer HTTP POST-Anforderung.</span><span class="sxs-lookup"><span data-stu-id="328cb-128">For example, using an HTTP POST request.</span></span> <span data-ttu-id="328cb-129">In einer blazor-Server-App befinden sich die Daten bereits auf dem Server, müssen jedoch persistent gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="328cb-129">In a Blazor Server app, the data is already on the server, but it must be persisted.</span></span> <span data-ttu-id="328cb-130">Die Handhabung des Datenzugriffs in blazor-Apps ist der Betreff des Abschnitts [Umgang mit Daten](data.md) .</span><span class="sxs-lookup"><span data-stu-id="328cb-130">Handling data access in Blazor apps is the subject of the [Dealing with data](data.md) section.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="328cb-131">Weitere Ressourcen</span><span class="sxs-lookup"><span data-stu-id="328cb-131">Additional resources</span></span>

<span data-ttu-id="328cb-132">Weitere Informationen zu [Formularen und zur Validierung](/aspnet/core/blazor/forms-validation) in blazor-apps finden Sie in der blazor-Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="328cb-132">For more information on [forms and validation](/aspnet/core/blazor/forms-validation) in Blazor apps, see the Blazor documentation.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="328cb-133">[Zurück](state-management.md)
>[Weiter](data.md)</span><span class="sxs-lookup"><span data-stu-id="328cb-133">[Previous](state-management.md)
[Next](data.md)</span></span>
