---
title: Formulare und Überprüfung
description: Erfahren Sie, wie Sie Formulare mit Client seitiger Validierung in Erstellen Blazor .
author: danroth27
ms.author: daroth
no-loc:
- Blazor
- Blazor WebAssembly
ms.date: 09/19/2019
ms.openlocfilehash: 1a99719f59415872510aef051d1f3c73daf53e15
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/09/2020
ms.locfileid: "86173275"
---
# <a name="forms-and-validation"></a>Formulare und Überprüfung

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

Das ASP.net Web Forms Framework enthält eine Reihe von Validierungsserver Steuerelementen, die das Validieren von Benutzereingaben verarbeiten, die in ein Formular eingegeben werden ( `RequiredFieldValidator` , `CompareValidator` , `RangeValidator` usw.). Das ASP.net Web Forms Framework unterstützt auch die Modell Bindung und die Validierung des Modells auf der Grundlage von Daten Anmerkungen ( `[Required]` , `[StringLength]` , `[Range]` usw.). Die Validierungs Logik kann sowohl auf dem Server als auch auf dem Client mithilfe unaufdringlicher JavaScript-basierter Validierung erzwungen werden. Das `ValidationSummary` Server Steuerelement wird verwendet, um eine Zusammenfassung der Validierungs Fehler für den Benutzer anzuzeigen.

Blazorunterstützt die Freigabe der Validierungs Logik zwischen dem Client und dem Server. ASP.net bietet vorgefertigte JavaScript-Implementierungen vieler allgemeiner Server Überprüfungen. In vielen Fällen muss der Entwickler trotzdem JavaScript schreiben, um seine App-spezifische Validierungs Logik vollständig zu implementieren. Die gleichen Modelltypen, Daten Anmerkungen und Validierungs Logik können sowohl auf dem Server als auch auf dem Client verwendet werden.

Blazorstellt einen Satz von Eingabe Komponenten bereit. Die Eingabe Komponenten behandeln die Bindungs Felddaten an ein Modell und validieren die Benutzereingaben, wenn das Formular übermittelt wird.

|Eingabekomponenten|Gerendertes Element HTML    |
|---------------|-------------------------|
|`InputCheckbox`|`<input type="checkbox">`|
|`InputDate`    |`<input type="date">`    |
|`InputNumber`  |`<input type="number">`  |
|`InputSelect`  |`<select>`               |
|`InputText`    |`<input>`                |
|`InputTextArea`|`<textarea>`             |

Die `EditForm` Komponente umschließt diese Eingabe Komponenten und orchestriert den Validierungsprozess über eine `EditContext` . Beim Erstellen eines- `EditForm` Parameters geben Sie an, welche Modell Instanz mit dem-Parameter gebunden werden soll `Model` . Die Validierung erfolgt in der Regel mithilfe von Daten Anmerkungen und ist erweiterbar. Um die auf Daten Anmerkungen basierende Validierung zu aktivieren, fügen Sie die `DataAnnotationsValidator` Komponente als untergeordnetes Element von hinzu `EditForm` . Die `EditForm` Komponente stellt ein nützliches Ereignis für die Behandlung gültiger ( `OnValidSubmit` ) und Ungültiger () Übermittlungen dar `OnInvalidSubmit` . Es gibt auch ein allgemeineres `OnSubmit` Ereignis, mit dem Sie die Überprüfung selbst auslösen und behandeln können.

Um eine Zusammenfassung der Überprüfungs Fehler anzuzeigen, verwenden Sie die- `ValidationSummary` Komponente. Verwenden Sie zum Anzeigen von Validierungs Meldungen für ein bestimmtes Eingabefeld die- `ValidationMessage` Komponente, und geben Sie einen Lambda-Ausdruck für den-Parameter an, `For` der auf den entsprechenden Modellmember zeigt.

Der folgende Modelltyp definiert mehrere Validierungsregeln mithilfe von Daten Anmerkungen:

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

Die folgende Komponente veranschaulicht das Erstellen eines Formulars in Blazor basierend auf dem `Starship` Modelltyp:

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

Nach der Übermittlung des Formulars wurden die Modell gebundenen Daten nicht in einem Datenspeicher gespeichert, wie z. b. einer Datenbank. In einer- Blazor WebAssembly App müssen die Daten an den Server gesendet werden. Beispielsweise mithilfe einer HTTP POST-Anforderung. In einer Blazor Server-App befinden sich die Daten bereits auf dem Server, müssen jedoch persistent gespeichert werden. Die Handhabung des Datenzugriffs in- Blazor Apps ist der Betreff des Abschnitts [Umgang mit Daten](data.md) .

## <a name="additional-resources"></a>Zusätzliche Ressourcen

Weitere Informationen zu [Formularen und zur Validierung](/aspnet/core/blazor/forms-validation) in- Blazor apps finden Sie in der- Blazor Dokumentation.

>[!div class="step-by-step"]
>[Zurück](state-management.md)
>[Weiter](data.md)
