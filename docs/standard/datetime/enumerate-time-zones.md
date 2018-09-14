---
title: 'Gewusst wie: Aufzählen der auf einem Computer vorhandenen Zeitzonen'
ms.date: 04/10/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- time zones [.NET Framework], enumerating
- enumerating time zones [.NET Framework]
ms.assetid: bb7a42ab-6bd9-4c5c-b734-5546d51f8669
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1c012b10f43a45699605e2d87a5b4a814c7dae28
ms.sourcegitcommit: 76a304c79a32aa13889ebcf4b9789a4542b48e3e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/13/2018
ms.locfileid: "45521595"
---
# <a name="how-to-enumerate-time-zones-present-on-a-computer"></a>Gewusst wie: Aufzählen der auf einem Computer vorhandenen Zeitzonen

Für die erfolgreiche Verarbeitung einer Zeitzone ist es erforderlich, dass dem System Informationen zu dieser Zeitzone zur Verfügung stehen. Die Betriebssysteme Windows XP und Windows Vista speichert diese Informationen in der Registrierung. Es gibt zwar sehr viele Zeitzonen auf der Welt, die Registrierung enthält aber nur Informationen zu einigen davon. Darüber hinaus ist die Registrierung selbst eine dynamische Struktur, deren Inhalt absichtlich oder aus Versehen geändert werden kann. Daher kann eine Anwendung nicht voraussetzen, dass eine bestimmte Zeitzone in einem System definiert und verfügbar ist. Bei vielen Anwendungen, die Zeitzoneninformationen verwenden, besteht der erste Schritt darin zu ermitteln, ob die erforderlichen Zeitzonen im lokalen System verfügbar sind, oder dem Benutzer eine Liste der Zeitzonen zur Auswahl zu bieten. Dafür wiederum muss eine Anwendung die im lokalen System definierten Zeitzonen aufzählen können.

> [!NOTE]
> Wenn eine Anwendung auf dem Vorhandensein einer bestimmten Zeitzone, die nicht in einem lokalen System definiert werden kann basiert, kann das Vorhandensein von die Anwendung sichergestellt werden, werden die Serialisierung und Deserialisierung von Informationen über die Zeitzone. Die Zeitzone kann ein Listensteuerelement dann hinzugefügt werden, damit Benutzer der Anwendung, die sie auswählen kann. Weitere Informationen finden Sie unter [Vorgehensweise: Speichern von Zeitzonen in einer eingebetteten Ressource](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md) und [Vorgehensweise: Wiederherstellen von Zeitzonen aus einer eingebetteten Ressource](../../../docs/standard/datetime/restore-time-zones-from-an-embedded-resource.md).

### <a name="to-enumerate-the-time-zones-present-on-the-local-system"></a>Aufzählen der im lokalen System vorhandenen Zeitzonen

1. Rufen Sie die <xref:System.TimeZoneInfo.GetSystemTimeZones%2A?displayProperty=nameWithType>-Methode auf. Die Methode gibt ein generisches <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> Auflistung von <xref:System.TimeZoneInfo> Objekte. Die Einträge in der Auflistung werden sortiert nach ihren <xref:System.TimeZoneInfo.DisplayName%2A> Eigenschaft. Zum Beispiel:

   [!code-csharp[System.TimeZone2.Concepts#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#1)]
   [!code-vb[System.TimeZone2.Concepts#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#1)]

2. Zählen Sie die einzelnen <xref:System.TimeZoneInfo> Objekte in der Auflistung mit einem `foreach` -Schleife (in c#) oder ein `For Each`...`Next` (in Visual Basic)-Schleife aus, und führen Sie alle erforderlichen Verarbeitungsschritte für jedes Objekt. Beispielsweise der folgende Code Listet die <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> Auflistung von <xref:System.TimeZoneInfo> Objekte der in Schritt 1 zurückgegeben und gibt den Anzeigenamen jeder Zeitzone in der Konsole.

   [!code-csharp[System.TimeZone2.Concepts#12](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#12)]
   [!code-vb[System.TimeZone2.Concepts#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#12)]

### <a name="to-present-the-user-with-a-list-of-time-zones-present-on-the-local-system"></a>Präsentieren Sie den Benutzer mit einer Liste der auf dem lokalen System vorhandenen Zeitzonen

1. Rufen Sie die <xref:System.TimeZoneInfo.GetSystemTimeZones%2A?displayProperty=nameWithType>-Methode auf. Die Methode gibt ein generisches <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> Auflistung von <xref:System.TimeZoneInfo> Objekte.

2. Weisen Sie in Schritt 1 zurückgegebene Auflistung der `DataSource` Eigenschaft von einer Windows Forms- oder ASP.NET-ANWENDUNGEN Listensteuerelement.

3. Abrufen der <xref:System.TimeZoneInfo> -Objekt, das der Benutzer ausgewählt hat.

Im Beispiel wird veranschaulicht, für eine Windows-Anwendung.

## <a name="example"></a>Beispiel

Das Beispiel startet eine Windows-Anwendung, die auf einem System in einem Listenfeld definierten Zeitzonen anzeigt. Das Beispiel zeigt ein Dialogfeld mit dem Wert der dann an die <xref:System.TimeZoneInfo.DisplayName%2A> -Eigenschaft des Objekts vom Benutzer ausgewählten Zeitzone.

[!code-csharp[System.TimeZone2.Concepts#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#2)]
[!code-vb[System.TimeZone2.Concepts#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#2)]

Die meisten Listen-Steuerelemente (z. B. die <xref:System.Windows.Forms.ListBox?displayProperty=nameWithType> oder <xref:System.Web.UI.WebControls.BulletedList?displayProperty=nameWithType> Steuerelement) ermöglichen es Ihnen, eine Auflistung von Objektvariablen zuzuweisen ihre `DataSource` Eigenschaft solange diese Auflistung implementiert die <xref:System.Collections.IEnumerable> Schnittstelle. (Die generische <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> -Klasse der Fall.) Um ein einzelnes Objekt in der Sammlung anzuzeigen, das Steuerelement dieses Objekts ruft `ToString` Methode, um die Zeichenfolge zu extrahieren, die zur Darstellung des Objekts verwendet wird. Im Fall von <xref:System.TimeZoneInfo> Objekte, die `ToString` Methode gibt die <xref:System.TimeZoneInfo> Anzeigename des Objekts (der Wert des der <xref:System.TimeZoneInfo.DisplayName%2A> Eigenschaft).

> [!NOTE]
> Da Listensteuerelemente eines Objekts aufrufen `ToString` Sie können die assign-Methode, einer Auflistung von <xref:System.TimeZoneInfo> Objekte an das Steuerelement, haben Sie das Steuerelement einen aussagekräftigen Namen für die einzelnen Objekte anzeigen, und rufen die <xref:System.TimeZoneInfo> -Objekt, das der Benutzer ausgewählt hat. Hierdurch entfällt die Notwendigkeit, eine Zeichenfolge für jedes Objekt in der Auflistung zu extrahieren, weisen Sie die Zeichenfolge eine Auflistung, die wiederum des Steuerelements zugewiesen ist `DataSource` Eigenschaft, rufen Sie die Zeichenfolge, die der Benutzer hat ausgewählt, und klicken Sie dann diese Zeichenfolge verwenden, um das Objekt zu extrahieren Es wird beschrieben. 

## <a name="compiling-the-code"></a>Kompilieren des Codes

Für dieses Beispiel benötigen Sie Folgendes:

* Dass das Projekt ein Verweis auf "System.Core.dll" hinzugefügt werden.

* Dass die folgenden Namespaces importiert werden:

  <xref:System> (im C#-Code)

  <xref:System.Collections.ObjectModel>

## <a name="see-also"></a>Siehe auch

* [Datumsangaben, Uhrzeiten und Zeitzonen](../../../docs/standard/datetime/index.md)
* [Vorgehensweise: Speichern von Zeitzonen in einer eingebetteten Ressource](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md)
* [Vorgehensweise: Wiederherstellen von Zeitzonen aus einer eingebetteten Ressource](../../../docs/standard/datetime/restore-time-zones-from-an-embedded-resource.md)
