---
title: 'Vorgehensweise: Auflisten von auf einem Computer vorhandenen Zeitzonen'
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
ms.openlocfilehash: dfdc3993f6658ce5dc50050ed062c2de9d4cec29
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-enumerate-time-zones-present-on-a-computer"></a>Vorgehensweise: Auflisten von auf einem Computer vorhandenen Zeitzonen

Für die erfolgreiche Verarbeitung einer Zeitzone ist es erforderlich, dass dem System Informationen zu dieser Zeitzone zur Verfügung stehen. Die Betriebssysteme Windows XP und Windows Vista speichert diese Informationen in der Registrierung. Es gibt zwar sehr viele Zeitzonen auf der Welt, die Registrierung enthält aber nur Informationen zu einigen davon. Darüber hinaus ist die Registrierung selbst eine dynamische Struktur, deren Inhalt absichtlich oder aus Versehen geändert werden kann. Daher kann eine Anwendung nicht voraussetzen, dass eine bestimmte Zeitzone in einem System definiert und verfügbar ist. Bei vielen Anwendungen, die Zeitzoneninformationen verwenden, besteht der erste Schritt darin zu ermitteln, ob die erforderlichen Zeitzonen im lokalen System verfügbar sind, oder dem Benutzer eine Liste der Zeitzonen zur Auswahl zu bieten. Dafür wiederum muss eine Anwendung die im lokalen System definierten Zeitzonen aufzählen können.

> [!NOTE]
> Wenn eine Anwendung auf dem Vorhandensein einer bestimmten Zeitzone, die nicht in einem lokalen System definiert werden kann benötigt, kann das Vorhandensein von die Anwendung sichergestellt werden, werden serialisieren und Deserialisieren von Informationen über die Zeitzone. Die Zeitzone kann ein Listenfeld-Steuerelement dann hinzugefügt werden, damit Benutzer der Anwendung, die sie auswählen kann. Weitere Informationen finden Sie unter [wie: Speichern von Zeitzonen in einer eingebetteten Ressource](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md) und [Vorgehensweise: Wiederherstellen von Zeitzonen aus einer eingebetteten Ressource](../../../docs/standard/datetime/restore-time-zones-from-an-embedded-resource.md).

### <a name="to-enumerate-the-time-zones-present-on-the-local-system"></a>Aufzählen der im lokalen System vorhandenen Zeitzonen

1. Rufen Sie die <xref:System.TimeZoneInfo.GetSystemTimeZones%2A?displayProperty=nameWithType>-Methode auf. Die Methode gibt eine generische <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> Auflistung von <xref:System.TimeZoneInfo> Objekte. Die Einträge in der Auflistung sind sortiert nach ihren <xref:System.TimeZoneInfo.DisplayName%2A> Eigenschaft. Zum Beispiel:

   [!code-csharp[System.TimeZone2.Concepts#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#1)]
   [!code-vb[System.TimeZone2.Concepts#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#1)]

2. Auflisten die einzelnen <xref:System.TimeZoneInfo> Objekte in der Auflistung mithilfe einer `foreach` -Schleife (in c#) oder eine `For Each`...`Next` (in Visual Basic)-Schleife aus, und führen Sie alle erforderlichen Verarbeitungsschritte für jedes Objekt. Z. B. der folgende Code Listet die <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> Auflistung von <xref:System.TimeZoneInfo> Objekte zurückgegebenen in Schritt 1 und der Anzeigename der einzelnen Zeitzonen in der Konsole aufgeführt.

   [!code-csharp[System.TimeZone2.Concepts#12](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#12)]
   [!code-vb[System.TimeZone2.Concepts#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#12)]

### <a name="to-present-the-user-with-a-list-of-time-zones-present-on-the-local-system"></a>Den Benutzer mit einer Liste der auf dem lokalen System enthaltenen Zeitzonen dar

1. Rufen Sie die <xref:System.TimeZoneInfo.GetSystemTimeZones%2A?displayProperty=nameWithType>-Methode auf. Die Methode gibt eine generische <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> Auflistung von <xref:System.TimeZoneInfo> Objekte.

2. Weisen Sie in Schritt 1 zurückgegebene Auflistung der `DataSource` Eigenschaft einer Windows Forms- oder ASP.NET-ANWENDUNGEN Listensteuerelement.

3. Abrufen der <xref:System.TimeZoneInfo> -Objekt, das der Benutzer ausgewählt hat.

Das Beispiel enthält ein Beispiel für eine Windows-Anwendung.

## <a name="example"></a>Beispiel

Das Beispiel startet eine Windows-Anwendung, die auf einem System in einem Listenfeld definierten Zeitzonen anzeigt. Im Beispiel zeigt ein Dialogfeld mit dem Wert der dann an die <xref:System.TimeZoneInfo.DisplayName%2A> -Eigenschaft des vom Benutzer ausgewählten Zeitzone-Objekts.

[!code-csharp[System.TimeZone2.Concepts#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#2)]
[!code-vb[System.TimeZone2.Concepts#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#2)]

Die meisten Listensteuerelemente (z. B. die <xref:System.Windows.Forms.ListBox?displayProperty=nameWithType> oder <xref:System.Web.UI.WebControls.BulletedList?displayProperty=nameWithType> Steuerelement) ermöglichen es Ihnen, eine Auflistung von Objektvariablen zuweisen ihre `DataSource` Eigenschaft solange diese Auflistung implementiert die <xref:System.Collections.IEnumerable> Schnittstelle. (Die generische <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> Klasse hierzu.) Um ein einzelnes Objekt in der Auflistung anzuzeigen, ruft das Steuerelement des Objekts `ToString` Methode, um die Zeichenfolge zu extrahieren, die verwendet wird, um das Objekt darstellen. Im Fall von <xref:System.TimeZoneInfo> Objekte, die `ToString` Methode gibt die <xref:System.TimeZoneInfo> Anzeigename des Objekts (der Wert des seine <xref:System.TimeZoneInfo.DisplayName%2A> Eigenschaft).

> [!NOTE]
> Da List-Steuerelemente des Objekts aufrufen `ToString` -Methode, können Sie eine Auflistung von zuweisen <xref:System.TimeZoneInfo> Objekte an das Steuerelement, damit das Steuerelement einen aussagekräftigen Namen für jedes Objekt anzeigen und Abrufen der <xref:System.TimeZoneInfo> -Objekt, das der Benutzer ausgewählt hat. Hierdurch entfällt die Notwendigkeit, eine Zeichenfolge für jedes Objekt in der Auflistung zu extrahieren, weisen Sie die Zeichenfolge für eine Sammlung, die wiederum an des Steuerelements zugewiesen ist `DataSource` -Eigenschaft, rufen Sie die Zeichenfolge, die der Benutzer ausgewählt hat, und klicken Sie dann diese Zeichenfolge verwenden, um das Objekt zu extrahieren beschrieben. 

## <a name="compiling-the-code"></a>Kompilieren des Codes

Für dieses Beispiel benötigen Sie Folgendes:

* Dem Projekt ein Verweis auf "System.Core.dll" hinzugefügt werden.

* Dass die folgenden Namespaces importiert werden:

  <xref:System> (in C#-Code)

  <xref:System.Collections.ObjectModel>

## <a name="see-also"></a>Siehe auch

[Datumsangaben, Uhrzeiten und Zeitzonen](../../../docs/standard/datetime/index.md)
[wie: Speichern von Zeitzonen in einer eingebetteten Ressource](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md)
[Vorgehensweise: Wiederherstellen von Zeitzonen aus einer eingebetteten Ressource](../../../docs/standard/datetime/restore-time-zones-from-an-embedded-resource.md)
