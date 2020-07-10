---
title: Architektur Vergleich von ASP.net-Web Forms undBlazor
description: Erfahren Sie, wie die Architekturen von ASP.net Web Forms und Blazor vergleichen.
author: danroth27
ms.author: daroth
no-loc:
- Blazor
ms.date: 09/11/2019
ms.openlocfilehash: 51b114c842e131ad9b9a589bf5137a522e135082
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/09/2020
ms.locfileid: "86173431"
---
# <a name="architecture-comparison-of-aspnet-web-forms-and-blazor"></a>Architektur Vergleich von ASP.net-Web Forms undBlazor

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

Obwohl ASP.net Web Forms und Blazor viele ähnliche Konzepte aufweisen, gibt es Unterschiede bei der Funktionsweise. In diesem Kapitel werden die inneren Abläufe und Architekturen von ASP.net Web Forms und untersucht Blazor .

## <a name="aspnet-web-forms"></a>ASP.NET Web Forms

ASP.net Web Forms Framework basiert auf einer Seiten zentrierten Architektur. Jede HTTP-Anforderung für einen Speicherort in der APP ist eine separate Seite, mit der ASP.net antwortet. Wenn Seiten angefordert werden, wird der Inhalt des Browsers durch die Ergebnisse der angeforderten Seite ersetzt.

Die Seiten bestehen aus den folgenden Komponenten:

- HTML-Markup
- C#- oder Visual Basic-Code
- Eine Code Behind-Klasse, die Logik-und Ereignis Behandlungs Funktionen enthält.
- Steuerelemente

Steuerelemente sind wiederverwendbare Einheiten der Webbenutzer Oberfläche, die Programm gesteuert auf einer Seite platziert und bearbeitet werden können. Seiten bestehen aus Dateien, die mit *aspx* enden, das Markup, Steuerelemente und Code enthält. Die Code-Behind-Klassen befinden sich in Dateien mit demselben Basis Namen und der Erweiterung " *. aspx.cs* " oder " *. aspx. vb* ", abhängig von der verwendeten Programmiersprache. Interessanterweise interpretiert der Webserver Inhalte der *aspx* -Dateien und kompiliert diese, wenn Sie sich ändern. Diese Neukompilierung findet auch dann statt, wenn der Webserver bereits ausgeführt wird.

Steuerelemente können mit Markup erstellt und als Benutzer Steuerelemente bereitgestellt werden. Ein Benutzer Steuerelement wird von der `UserControl` -Klasse abgeleitet und verfügt über eine ähnliche Struktur wie die Seite. Markup für Benutzer Steuerelemente wird in einer *ASCX* -Datei gespeichert. Eine zugehörige Code Behind-Klasse befindet sich in einer *. ascx.cs* -oder *ascx. vb* -Datei. Steuerelemente können auch vollständig mit Code erstellt werden, indem entweder von der-oder der- `WebControl` `CompositeControl` Basisklasse geerbt wird.

Seiten verfügen auch über einen umfangreichen Ereignis Lebenszyklus. Jede Seite löst Ereignisse für die Initialisierungs-, Auslastungs-, PreRender-und Entlade Ereignisse aus, die auftreten, wenn die ASP.NET-Laufzeit den Code der Seite für jede Anforderung ausführt.

Steuerelemente auf einer Seite werden in der Regel auf dieselbe Seite zurückgesendet, die das Steuerelement präsentiert hat, und mit Ihnen eine Nutzlast aus einem verborgenen Formularfeld mit dem Namen `ViewState` . Das- `ViewState` Feld enthält Informationen über den Zustand der Steuerelemente zu dem Zeitpunkt, an dem Sie gerendert und auf der Seite dargestellt wurden, sodass die ASP.NET-Laufzeit Änderungen an dem an den Server gesendeten Inhalt vergleichen und identifizieren kann.

## Blazor

Blazorist ein Client seitiges Webbenutzer Oberflächen-Framework, das in der Art von JavaScript-Front-End-Frameworks wie Angular oder reagieren ähnlich ist. Blazorbehandelt Benutzerinteraktionen und rendert die erforderlichen Aktualisierungen der Benutzeroberfläche. Blazorbasiert *nicht* auf einem Anforderungs-Antwort-Modell. Benutzerinteraktionen werden als Ereignisse behandelt, die sich nicht im Kontext einer bestimmten HTTP-Anforderung befinden.

BlazorApps bestehen aus einer oder mehreren Stamm Komponenten, die auf einer HTML-Seite gerendert werden.

![BlazorKomponenten in HTML](./media/architecture-comparison/blazor-components-in-html.png)

Die Art und Weise, wie der Benutzer angibt, wo Komponenten dargestellt werden sollen und wie die Komponenten dann für Benutzerinteraktionen miteinander verknüpft werden, ist das [Hostingmodell](hosting-models.md) .

Blazor[Komponenten](components.md) sind .NET-Klassen, die eine wiederverwendbare Benutzeroberfläche darstellen. Jede Komponente behält ihren eigenen Zustand bei und gibt Ihre eigene Renderinglogik an, die das Rendering anderer Komponenten einschließen kann. Komponenten geben Ereignishandler für bestimmte Benutzerinteraktionen an, um den Status der Komponente zu aktualisieren.

Nachdem eine Komponente ein Ereignis verarbeitet hat, wird Blazor die Komponente von gerendert und verfolgt, was sich in der gerenderten Ausgabe geändert hat. Komponenten werden nicht direkt in die Dokumentobjektmodell (DOM). Stattdessen werden Sie in einer Speicher internen Darstellung des DOM mit dem Namen dargestellt, `RenderTree` sodass Blazor die Änderungen nachverfolgt werden können. BlazorVergleicht die neu gerenderte Ausgabe mit der vorherigen Ausgabe, um einen Benutzeroberflächen diff zu berechnen, der dann effizient auf das DOM angewendet wird.

![BlazorDOM-Interaktion](./media/architecture-comparison/blazor-dom-interaction.png)

Komponenten können auch manuell angeben, dass Sie gerendert werden sollen, wenn sich Ihr Status außerhalb eines normalen Benutzeroberflächen Ereignisses ändert. Blazor verwendet eine `SynchronizationContext`-Eigenschaft, um einen einzelnen logischen Ausführungsthread zu erzwingen. Die Lebenszyklusmethoden einer Komponente und alle Ereignisrückrufe, die von Blazor ausgelöst werden, werden in dieser `SynchronizationContext`-Eigenschaft ausgeführt.

>[!div class="step-by-step"]
>[Zurück](introduction.md)
>[Weiter](hosting-models.md)
