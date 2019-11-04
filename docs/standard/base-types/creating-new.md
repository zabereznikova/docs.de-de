---
title: Erstellen neuer Zeichenfolgen in .NET
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- CopyTo method
- Join method
- Format method
- Concat method
- strings [.NET Framework], creating
- Insert method
ms.assetid: 06fdf123-2fac-4459-8904-eb48ab908a30
ms.openlocfilehash: ef65c50111d6ba91ab70d0b9c8cb90c606f9366c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73103820"
---
# <a name="creating-new-strings-in-net"></a>Erstellen neuer Zeichenfolgen in .NET
.NET Framework ermöglicht das Erstellen von Zeichenfolgen mithilfe einer einfachen Zuweisung und überlädt auch einen Klassenkonstruktor, um die Zeichenfolgenerstellung mithilfe einer Reihe verschiedener Parameter zu unterstützen. .NET Framework stellt auch verschiedene Methoden in der <xref:System.String?displayProperty=nameWithType>-Klasse bereit, die durch das Kombinieren verschiedener Zeichenfolgen, Zeichenfolgenarrays oder Objekte neue Zeichenfolgenobjekte erstellen.  
  
## <a name="creating-strings-using-assignment"></a>Erstellen von Zeichenfolgen mithilfe von Zuweisung  
 Die einfachste Möglichkeit, ein neues <xref:System.String>-Objekt zu erstellen, ist die Zuweisung eines Zeichenfolgenliterals zu einem <xref:System.String>-Objekt.  
  
## <a name="creating-strings-using-a-class-constructor"></a>Erstellen von Zeichenfolgen mithilfe eines Klassenkonstruktors  
 Sie können Überladungen des <xref:System.String>-Klassenkonstruktors verwenden, um Zeichenfolgen aus Zeichenarrays zu erstellen. Sie können auch eine neue Zeichenfolge erstellen, indem Sie ein bestimmtes Zeichen eine angegebene Anzahl von Malen duplizieren.  
  
## <a name="methods-that-return-strings"></a>Methoden, die Zeichenfolgen zurückgeben  
 Die folgende Tabelle führt verschiedene nützliche Methoden auf, die neue Zeichenfolgenobjekte zurückgeben.  
  
|Methodenname|Verwendung|  
|-----------------|---------|  
|<xref:System.String.Format%2A?displayProperty=nameWithType>|Erstellt eine formatierte Zeichenfolge aus einem Satz von Eingabeobjekten.|  
|<xref:System.String.Concat%2A?displayProperty=nameWithType>|Erstellt Zeichenfolgen aus mindestens zwei Zeichenfolgen.|  
|<xref:System.String.Join%2A?displayProperty=nameWithType>|Erstellt eine neue Zeichenfolge durch Kombinieren eines Arrays aus Zeichenfolgen.|  
|<xref:System.String.Insert%2A?displayProperty=nameWithType>|Erstellt eine neue Zeichenfolge durch Einfügen einer Zeichenfolge in den angegebenen Index einer vorhandenen Zeichenfolge.|  
|<xref:System.String.CopyTo%2A?displayProperty=nameWithType>|Kopiert angegebene Zeichen in einer Zeichenfolge in eine bestimmte Position in einem Array aus Zeichen.|  
  
### <a name="format"></a>Format  
 Sie können die **String.Format**-Methode verwenden, um formatierte Zeichenfolgen zu erstellen und Zeichenfolgen zu verketten, die mehrere Objekte darstellen. Diese Methode konvertiert automatisch alle übergebenen Objekte in eine Zeichenfolge. Wenn Ihre Anwendung z.B. dem Benutzer einen **Int32**-Wert und einen **DateTime**-Wert anzeigen soll, können Sie ganz einfach mithilfe der **Format**-Methode eine Zeichenfolge erstellen, um diese Werte darzustellen. Informationen zu den mit dieser Methode verwendeten Formatierungskonventionen finden Sie im Abschnitt [Zusammengesetzte Formatierung](../../../docs/standard/base-types/composite-formatting.md).  
  
 Das folgende Beispiel verwendet die **Format**-Methode, um eine Zeichenfolge zu erstellen, die eine ganzzahlige Variable verwendet.  
  
 [!code-csharp[Strings.Creating#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Strings.Creating/cs/Example.cs#1)]
 [!code-vb[Strings.Creating#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Strings.Creating/vb/Example.vb#1)]  
  
 In diesem Beispiel zeigt <xref:System.DateTime.Now%2A?displayProperty=nameWithType> das aktuelle Datum und die aktuelle Uhrzeit so an, wie es von der mit dem aktuellen Thread verknüpften Kultur angegeben ist.  
  
### <a name="concat"></a>Concat  
 Die **String.Concat**-Methode kann verwendet werden, um ganz einfach aus mindestens zwei vorhandenen Objekten ein neues Zeichenfolgenobjekt zu erstellen. Die Methode bietet eine sprachunabhängige Möglichkeit zum Verketten von Zeichenfolgen. Diese Methode akzeptiert alle von **System.Object** abgeleiteten Klassen. Das folgende Beispiel erstellt eine Zeichenfolge aus zwei vorhandenen Zeichenfolgenobjekten und einem Trennzeichen.  
  
 [!code-csharp[Strings.Creating#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Strings.Creating/cs/Example.cs#2)]
 [!code-vb[Strings.Creating#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Strings.Creating/vb/Example.vb#2)]  
  
### <a name="join"></a>Join  
 Die **String.Join**-Methode erstellt eine neue Zeichenfolge aus einem Array aus Zeichenfolgen und einem Trennzeichen. Diese Methode ist nützlich, wenn Sie mehrere Zeichenfolgen miteinander verketten möchten. Sie erstellt eine Liste, die z.B. durch ein Komma getrennt sein kann.  
  
 Das folgende Beispiel verwendet ein Leerzeichen, um ein Zeichenfolgenarray zu binden.  
  
 [!code-csharp[Strings.Creating#3](../../../samples/snippets/csharp/VS_Snippets_CLR/Strings.Creating/cs/Example.cs#3)]
 [!code-vb[Strings.Creating#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Strings.Creating/vb/Example.vb#3)]  
  
### <a name="insert"></a>Insert  
 Die **String.Insert**-Methode erstellt eine neue Zeichenfolge, indem sie eine Zeichenfolge an einer angegebenen Position in einer anderen Zeichenfolge einfügt. Diese Methode verwendet einen nullbasierten Index. Das folgende Beispiel fügt eine Zeichenfolge an der fünften Indexposition von `MyString` ein und erstellt mit diesem Wert eine neue Zeichenfolge.  
  
 [!code-csharp[Strings.Creating#4](../../../samples/snippets/csharp/VS_Snippets_CLR/Strings.Creating/cs/Example.cs#4)]
 [!code-vb[Strings.Creating#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Strings.Creating/vb/Example.vb#4)]  
  
### <a name="copyto"></a>CopyTo  
 Die **String.CopyTo**-Methode kopiert Teile einer Zeichenfolge in ein Zeichenarray. Sie können sowohl den Startindex der Zeichenfolge als auch die Anzahl der zu kopierenden Zeichen angeben. Diese Methode akzeptiert den Quellindex, ein Array aus Zeichen, den Zielindex und die Anzahl der zu kopierenden Zeichen. Alle Indizes sind nullbasiert.  
  
 Das folgende Beispiel verwendet die **CopyTo**-Methode, um die Zeichen des Worts „Hello“ aus einem Zeichenfolgenobjekt in die erste Indexposition eines Zeichenarrays zu kopieren.  
  
 [!code-csharp[Strings.Creating#5](../../../samples/snippets/csharp/VS_Snippets_CLR/Strings.Creating/cs/Example.cs#5)]
 [!code-vb[Strings.Creating#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Strings.Creating/vb/Example.vb#5)]  
  
## <a name="see-also"></a>Siehe auch

- [Grundlegende Zeichenfolgenoperationen](../../../docs/standard/base-types/basic-string-operations.md)
- [Kombinierte Formatierung](../../../docs/standard/base-types/composite-formatting.md)
