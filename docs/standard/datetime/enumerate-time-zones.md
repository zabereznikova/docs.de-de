---
title: 'Vorgehensweise: Aufzählen der auf einem Computer vorhandenen Zeitzonen'
ms.date: 04/10/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- time zones [.NET], enumerating
- enumerating time zones [.NET]
ms.assetid: bb7a42ab-6bd9-4c5c-b734-5546d51f8669
ms.openlocfilehash: a51e9d0c51968d57e0d79dd80d8619ab11cdbf93
ms.sourcegitcommit: b1442669f1982d3a1cb18ea35b5acfb0fc7d93e4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2020
ms.locfileid: "93063767"
---
# <a name="how-to-enumerate-time-zones-present-on-a-computer"></a>Vorgehensweise: Aufzählen der auf einem Computer vorhandenen Zeitzonen

Für die erfolgreiche Verarbeitung einer Zeitzone ist es erforderlich, dass dem System Informationen zu dieser Zeitzone zur Verfügung stehen. Die Betriebssysteme Windows XP und Windows Vista speichern diese Informationen in der Registrierung. Es gibt zwar sehr viele Zeitzonen auf der Welt, die Registrierung enthält aber nur Informationen zu einigen davon. Darüber hinaus ist die Registrierung selbst eine dynamische Struktur, deren Inhalt absichtlich oder aus Versehen geändert werden kann. Daher kann eine Anwendung nicht voraussetzen, dass eine bestimmte Zeitzone in einem System definiert und verfügbar ist. Bei vielen Anwendungen, die Zeitzoneninformationen verwenden, besteht der erste Schritt darin zu ermitteln, ob die erforderlichen Zeitzonen im lokalen System verfügbar sind, oder dem Benutzer eine Liste der Zeitzonen zur Auswahl zu bieten. Dafür wiederum muss eine Anwendung die im lokalen System definierten Zeitzonen aufzählen können.

> [!NOTE]
> Wenn eine Anwendung davon abhängt, dass eine bestimmte Zeitzone vorhanden ist, die möglicherweise nicht auf einem lokalen System definiert ist, kann die Anwendung ihre Anwesenheit durch serialisieren und Deserialisieren von Informationen über die Zeitzone sicherstellen. Die Zeitzone kann dann einem Listen Steuerelement hinzugefügt werden, sodass Sie vom Anwendungs Benutzer ausgewählt werden kann. Weitere Informationen finden Sie unter Gewusst [wie: Speichern von Zeitzonen in einer eingebetteten Ressource](save-time-zones-to-an-embedded-resource.md) und Gewusst [wie: Wiederherstellen von Zeitzonen aus einer eingebetteten Ressource](restore-time-zones-from-an-embedded-resource.md).

### <a name="to-enumerate-the-time-zones-present-on-the-local-system"></a>Aufzählen der im lokalen System vorhandenen Zeitzonen

1. Rufen Sie die <xref:System.TimeZoneInfo.GetSystemTimeZones%2A?displayProperty=nameWithType>-Methode auf. Die-Methode gibt eine generische Auflistung <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> von- <xref:System.TimeZoneInfo> Objekten zurück. Die Einträge in der Auflistung werden nach der- <xref:System.TimeZoneInfo.DisplayName%2A> Eigenschaft sortiert. Beispiel:

   [!code-csharp[System.TimeZone2.Concepts#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#1)]
   [!code-vb[System.TimeZone2.Concepts#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#1)]

2. Auflisten der einzelnen <xref:System.TimeZoneInfo> Objekte in der Auflistung mit einer- `foreach` Schleife (in c#) oder einem `For Each` ...`Next` -Schleife (in Visual Basic), und führen Sie alle erforderlichen Verarbeitungsschritte für jedes-Objekt aus. Der folgende Code listet z. b. die Auflistung <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> von <xref:System.TimeZoneInfo> -Objekten auf, die in Schritt 1 zurückgegeben wurden, und listet den anzeigen Amen jeder Zeitzone in der Konsole auf.

   [!code-csharp[System.TimeZone2.Concepts#12](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#12)]
   [!code-vb[System.TimeZone2.Concepts#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#12)]

### <a name="to-present-the-user-with-a-list-of-time-zones-present-on-the-local-system"></a>So präsentieren Sie dem Benutzer eine Liste der Zeitzonen, die auf dem lokalen System vorhanden sind

1. Rufen Sie die <xref:System.TimeZoneInfo.GetSystemTimeZones%2A?displayProperty=nameWithType>-Methode auf. Die-Methode gibt eine generische Auflistung <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> von- <xref:System.TimeZoneInfo> Objekten zurück.

2. Weisen Sie die in Schritt 1 zurückgegebene Auflistung der- `DataSource` Eigenschaft eines Windows Forms-oder ASP.net List-Steuer Elements zu.

3. Ruft das <xref:System.TimeZoneInfo> Objekt ab, das der Benutzer ausgewählt hat.

Das Beispiel enthält eine Abbildung für eine Windows-Anwendung.

## <a name="example"></a>Beispiel

Im Beispiel wird eine Windows-Anwendung gestartet, die die in einem System definierten Zeitzonen in einem Listenfeld anzeigt. Im Beispiel wird dann ein Dialogfeld angezeigt, das den Wert der- <xref:System.TimeZoneInfo.DisplayName%2A> Eigenschaft des Zeit Zonen Objekts enthält, das vom Benutzer ausgewählt wurde.

[!code-csharp[System.TimeZone2.Concepts#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#2)]
[!code-vb[System.TimeZone2.Concepts#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#2)]

Die meisten Listen Steuerelemente (z. b. das-Steuerelement oder das- <xref:System.Windows.Forms.ListBox?displayProperty=nameWithType> <xref:System.Web.UI.WebControls.BulletedList?displayProperty=nameWithType> Steuerelement) ermöglichen es Ihnen, der-Eigenschaft eine Auflistung von Objektvariablen zuzuweisen, solange `DataSource` diese Auflistung die- <xref:System.Collections.IEnumerable> Schnittstelle (Die generische- <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> Klasse führt dies aus.) Um ein einzelnes Objekt in der Auflistung anzuzeigen, ruft das-Steuerelement die-Methode dieses Objekts `ToString` auf, um die Zeichenfolge zu extrahieren, die für die Darstellung des Objekts verwendet wird. Bei <xref:System.TimeZoneInfo> `ToString` -Objekten gibt die-Methode den <xref:System.TimeZoneInfo> anzeigen amen des-Objekts zurück (den Wert der- <xref:System.TimeZoneInfo.DisplayName%2A> Eigenschaft).

> [!NOTE]
> Da Listen Steuerelemente die-Methode eines Objekts aufrufen `ToString` , können Sie dem Steuerelement eine Auflistung von-Objekten zuweisen, festlegen, <xref:System.TimeZoneInfo> dass das Steuerelement einen aussagekräftigen Namen für jedes Objekt anzeigt, und das Objekt abrufen, das <xref:System.TimeZoneInfo> der Benutzer ausgewählt hat. Dadurch entfällt die Notwendigkeit, eine Zeichenfolge für jedes Objekt in der Auflistung zu extrahieren, die Zeichenfolge einer Auflistung zuzuweisen, die wiederum der-Eigenschaft des-Steuer Elements zugewiesen ist `DataSource` , die vom Benutzer ausgewählte Zeichenfolge abzurufen und diese Zeichenfolge zu extrahieren, um das Objekt zu extrahieren, das Sie beschreibt.

## <a name="compiling-the-code"></a>Kompilieren des Codes

Für dieses Beispiel benötigen Sie Folgendes:

- Die folgenden Namespaces werden importiert:

  <xref:System> (in c#-Code)

  <xref:System.Collections.ObjectModel>

## <a name="see-also"></a>Siehe auch

- [Datumsangaben, Uhrzeiten und Zeitzonen](index.md)
- [Gewusst wie: Speichern von Zeitzonen in einer eingebetteten Ressource](save-time-zones-to-an-embedded-resource.md)
- [Vorgehensweise: Wiederherstellen von Zeitzonen aus einer eingebetteten Ressource](restore-time-zones-from-an-embedded-resource.md)
