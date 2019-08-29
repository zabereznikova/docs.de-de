---
title: 'Vorgehensweise: Aufzählen der auf einem Computer vorhandenen Zeitzonen'
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
ms.openlocfilehash: afc3b57659dd6719f72cefba8a6d2f1abe08c0d0
ms.sourcegitcommit: 6f28b709592503d27077b16fff2e2eacca569992
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/28/2019
ms.locfileid: "70106653"
---
# <a name="how-to-enumerate-time-zones-present-on-a-computer"></a>Vorgehensweise: Aufzählen der auf einem Computer vorhandenen Zeitzonen

Für die erfolgreiche Verarbeitung einer Zeitzone ist es erforderlich, dass dem System Informationen zu dieser Zeitzone zur Verfügung stehen. Die Betriebssysteme Windows XP und Windows Vista speichern diese Informationen in der Registrierung. Es gibt zwar sehr viele Zeitzonen auf der Welt, die Registrierung enthält aber nur Informationen zu einigen davon. Darüber hinaus ist die Registrierung selbst eine dynamische Struktur, deren Inhalt absichtlich oder aus Versehen geändert werden kann. Daher kann eine Anwendung nicht voraussetzen, dass eine bestimmte Zeitzone in einem System definiert und verfügbar ist. Bei vielen Anwendungen, die Zeitzoneninformationen verwenden, besteht der erste Schritt darin zu ermitteln, ob die erforderlichen Zeitzonen im lokalen System verfügbar sind, oder dem Benutzer eine Liste der Zeitzonen zur Auswahl zu bieten. Dafür wiederum muss eine Anwendung die im lokalen System definierten Zeitzonen aufzählen können.

> [!NOTE]
> Wenn eine Anwendung davon abhängt, dass eine bestimmte Zeitzone vorhanden ist, die möglicherweise nicht auf einem lokalen System definiert ist, kann die Anwendung ihre Anwesenheit durch serialisieren und Deserialisieren von Informationen über die Zeitzone sicherstellen. Die Zeitzone kann dann einem Listen Steuerelement hinzugefügt werden, sodass Sie vom Anwendungs Benutzer ausgewählt werden kann. Weitere Informationen finden Sie unter [Vorgehensweise: Speichern von Zeitzonen in einer eingebetteten Ressource](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md) und [Gewusst wie: Stellen Sie Zeitzonen aus einer eingebetteten Ressource](../../../docs/standard/datetime/restore-time-zones-from-an-embedded-resource.md)wieder her.

### <a name="to-enumerate-the-time-zones-present-on-the-local-system"></a>Aufzählen der im lokalen System vorhandenen Zeitzonen

1. Rufen Sie die <xref:System.TimeZoneInfo.GetSystemTimeZones%2A?displayProperty=nameWithType>-Methode auf. Die-Methode gibt eine <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> generische Auflistung <xref:System.TimeZoneInfo> von-Objekten zurück. Die Einträge in der Auflistung werden nach <xref:System.TimeZoneInfo.DisplayName%2A> der-Eigenschaft sortiert. Zum Beispiel:

   [!code-csharp[System.TimeZone2.Concepts#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#1)]
   [!code-vb[System.TimeZone2.Concepts#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#1)]

2. Auflisten der einzelnen <xref:System.TimeZoneInfo> Objekte in der Auflistung mit einer `foreach` -Schleife (in C#) oder einem `For Each`...`Next` -Schleife (in Visual Basic), und führen Sie alle erforderlichen Verarbeitungsschritte für jedes-Objekt aus. Der folgende Code listet z. b. die <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> Auflistung von <xref:System.TimeZoneInfo> -Objekten auf, die in Schritt 1 zurückgegeben wurden, und listet den anzeigen Amen jeder Zeitzone in der Konsole auf.

   [!code-csharp[System.TimeZone2.Concepts#12](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#12)]
   [!code-vb[System.TimeZone2.Concepts#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#12)]

### <a name="to-present-the-user-with-a-list-of-time-zones-present-on-the-local-system"></a>So präsentieren Sie dem Benutzer eine Liste der Zeitzonen, die auf dem lokalen System vorhanden sind

1. Rufen Sie die <xref:System.TimeZoneInfo.GetSystemTimeZones%2A?displayProperty=nameWithType>-Methode auf. Die-Methode gibt eine <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> generische Auflistung <xref:System.TimeZoneInfo> von-Objekten zurück.

2. Weisen Sie die in Schritt 1 zurückgegebene Auflistung `DataSource` der-Eigenschaft eines Windows Forms-oder ASP.net List-Steuer Elements zu.

3. Ruft das <xref:System.TimeZoneInfo> Objekt ab, das der Benutzer ausgewählt hat.

Das Beispiel enthält eine Abbildung für eine Windows-Anwendung.

## <a name="example"></a>Beispiel

Im Beispiel wird eine Windows-Anwendung gestartet, die die in einem System definierten Zeitzonen in einem Listenfeld anzeigt. Im Beispiel wird dann ein Dialogfeld angezeigt, das den Wert der <xref:System.TimeZoneInfo.DisplayName%2A> -Eigenschaft des Zeit Zonen Objekts enthält, das vom Benutzer ausgewählt wurde.

[!code-csharp[System.TimeZone2.Concepts#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#2)]
[!code-vb[System.TimeZone2.Concepts#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#2)]

Die meisten Listen Steuerelemente (z <xref:System.Windows.Forms.ListBox?displayProperty=nameWithType> . <xref:System.Web.UI.WebControls.BulletedList?displayProperty=nameWithType> b. das-Steuerelement oder das-Steuerelement) ermöglichen `DataSource` es Ihnen, der-Eigenschaft eine Auflistung <xref:System.Collections.IEnumerable> von Objektvariablen zuzuweisen, solange diese Auflistung die-Schnittstelle (Die generische <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> -Klasse führt dies aus.) Um ein einzelnes Objekt in der Auflistung anzuzeigen, ruft das-Steuerelement die `ToString` -Methode dieses Objekts auf, um die Zeichenfolge zu extrahieren, die für die Darstellung des Objekts verwendet wird. Bei-Objekten gibt die `ToString` -Methode den anzeigen Amen <xref:System.TimeZoneInfo> des-Objekts zurück (den Wert der- Eigenschaft).<xref:System.TimeZoneInfo.DisplayName%2A> <xref:System.TimeZoneInfo>

> [!NOTE]
> Da Listen Steuerelemente die- `ToString` Methode eines Objekts aufrufen, können Sie dem Steuerelement eine Auflistung von <xref:System.TimeZoneInfo> -Objekten zuweisen, festlegen, dass das Steuerelement einen aussagekräftigen Namen für <xref:System.TimeZoneInfo> jedes Objekt anzeigt, und das Objekt abrufen, das der Benutzer ausgewählt hat. Dadurch entfällt die Notwendigkeit, eine Zeichenfolge für jedes Objekt in der Auflistung zu extrahieren, die Zeichenfolge einer Auflistung zuzuweisen, die wiederum der- `DataSource` Eigenschaft des Steuer Elements zugewiesen ist, die vom Benutzer ausgewählte Zeichenfolge abzurufen und diese Zeichenfolge zum Extrahieren des Objekts zu verwenden. Das wird beschrieben. 

## <a name="compiling-the-code"></a>Kompilieren des Codes

Für dieses Beispiel benötigen Sie Folgendes:

- Die folgenden Namespaces werden importiert:

  <xref:System>(im C# Code)

  <xref:System.Collections.ObjectModel>

## <a name="see-also"></a>Siehe auch

- [Datumsangaben, Uhrzeiten und Zeitzonen](../../../docs/standard/datetime/index.md)
- [Vorgehensweise: Speichern von Zeitzonen in einer eingebetteten Ressource](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md)
- [Vorgehensweise: Wiederherstellen von Zeitzonen aus einer eingebetteten Ressource](../../../docs/standard/datetime/restore-time-zones-from-an-embedded-resource.md)
