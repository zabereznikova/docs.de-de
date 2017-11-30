---
title: Erstellen neuer Zeichenfolgen in .NET
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d000cd88fc9ee9fd48ef25e9bb4982688564a2a0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="creating-new-strings-in-net"></a>Erstellen neuer Zeichenfolgen in .NET
Die [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] können Zeichenfolgen, die mit einfachen Zuordnung erstellt werden, und überlädt auch einen Klassenkonstruktor zum Erstellen von Zeichenfolgen mit einer Reihe von unterschiedlichen Parametern zu unterstützen. Die [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] auch stellt mehrere Methoden in der <xref:System.String?displayProperty=nameWithType> -Klasse, die neue Zeichenfolge erstellt Objekte nach Kombination von mehreren Zeichenfolgen, Arrays von Zeichenfolgen oder Objekte.  
  
## <a name="creating-strings-using-assignment"></a>Erstellen von Zeichenfolgen mithilfe von Zuweisung  
 Die einfachste Möglichkeit zum Erstellen eines neuen <xref:System.String> Objekt besteht darin, ein Zeichenfolgenliteral in weisen eine <xref:System.String> Objekt.  
  
## <a name="creating-strings-using-a-class-constructor"></a>Erstellen von Zeichenfolgen mithilfe eines Klassenkonstruktors  
 Können Sie Überladungen von der <xref:System.String> Klassenkonstruktor Zeichenfolgen aus Zeichenarrays zu erstellen. Sie können auch eine neue Zeichenfolge erstellen, indem Sie ein bestimmtes Zeichen eine angegebene Anzahl von Malen duplizieren.  
  
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
 Sie können die **String.Format** -Methode formatierte Zeichenfolgen erstellen und Verketten von Zeichenfolgen, die mehrere Objekte darstellt. Diese Methode konvertiert automatisch alle übergebenen Objekte in eine Zeichenfolge. Z. B., wenn die Anwendung angezeigt, muss eine **Int32** Wert und eine **"DateTime"** Wert für den Benutzer können Sie problemlos eine Zeichenfolge, um diese Werte über darstellen erstellen die **Format**Methode. Informationen zu den mit dieser Methode verwendeten Formatierungskonventionen finden Sie im Abschnitt [Zusammengesetzte Formatierung](../../../docs/standard/base-types/composite-formatting.md).  
  
 Im folgenden Beispiel wird die **Format** Methode, um eine Zeichenfolge zu erstellen, der eine ganzzahlige Variable verwendet.  
  
 [!code-csharp[Strings.Creating#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Strings.Creating/cs/Example.cs#1)]
 [!code-vb[Strings.Creating#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Strings.Creating/vb/Example.vb#1)]  
  
 In diesem Beispiel<xref:System.DateTime.Now%2A?displayProperty=nameWithType> zeigt das aktuelle Datum und die Uhrzeit in einer Weise angegeben, die von der Kultur, die dem aktuellen Thread zugeordnet.  
  
### <a name="concat"></a>Concat  
 Die **String.Concat** Methode kann verwendet werden, um ein neues Zeichenfolgeobjekt problemlos aus zwei oder mehr vorhandene Objekte zu erstellen. Die Methode bietet eine sprachunabhängige Möglichkeit zum Verketten von Zeichenfolgen. Diese Methode akzeptiert jede Klasse, die abgeleitet **System.Object**. Das folgende Beispiel erstellt eine Zeichenfolge aus zwei vorhandenen Zeichenfolgenobjekten und einem Trennzeichen.  
  
 [!code-csharp[Strings.Creating#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Strings.Creating/cs/Example.cs#2)]
 [!code-vb[Strings.Creating#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Strings.Creating/vb/Example.vb#2)]  
  
### <a name="join"></a>Join  
 Die **String.Join** Methode erstellt eine neue Zeichenfolge aus einem Array von Zeichenfolgen und ein Trennzeichen. Diese Methode ist nützlich, wenn Sie mehrere Zeichenfolgen miteinander verketten möchten. Sie erstellt eine Liste, die z.B. durch ein Komma getrennt sein kann.  
  
 Das folgende Beispiel verwendet ein Leerzeichen, um ein Zeichenfolgenarray zu binden.  
  
 [!code-csharp[Strings.Creating#3](../../../samples/snippets/csharp/VS_Snippets_CLR/Strings.Creating/cs/Example.cs#3)]
 [!code-vb[Strings.Creating#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Strings.Creating/vb/Example.vb#3)]  
  
### <a name="insert"></a>Insert  
 Die **String.Insert** Methode erstellt eine neue Zeichenfolge, indem eine Zeichenfolge in einer angegebenen Position in einer anderen Zeichenfolge eingefügt. Diese Methode verwendet einen nullbasierten Index. Das folgende Beispiel fügt eine Zeichenfolge an der fünften Indexposition von `MyString` ein und erstellt mit diesem Wert eine neue Zeichenfolge.  
  
 [!code-csharp[Strings.Creating#4](../../../samples/snippets/csharp/VS_Snippets_CLR/Strings.Creating/cs/Example.cs#4)]
 [!code-vb[Strings.Creating#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Strings.Creating/vb/Example.vb#4)]  
  
### <a name="copyto"></a>CopyTo  
 Die **String.CopyTo** Methode kopiert die Teile einer Zeichenfolge in ein Array von Zeichen. Sie können sowohl den Startindex der Zeichenfolge als auch die Anzahl der zu kopierenden Zeichen angeben. Diese Methode akzeptiert den Quellindex, ein Array aus Zeichen, den Zielindex und die Anzahl der zu kopierenden Zeichen. Alle Indizes sind nullbasiert.  
  
 Im folgenden Beispiel wird die **CopyTo** Methode, um die Zeichen des Worts "Hello" aus einer Zeichenfolge Objekt kopieren, an die erste Indexposition eines Arrays von Zeichen.  
  
 [!code-csharp[Strings.Creating#5](../../../samples/snippets/csharp/VS_Snippets_CLR/Strings.Creating/cs/Example.cs#5)]
 [!code-vb[Strings.Creating#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Strings.Creating/vb/Example.vb#5)]  
  
## <a name="see-also"></a>Siehe auch  
 [Grundlegende Zeichenfolgenoperationen](../../../docs/standard/base-types/basic-string-operations.md)  
 [Kombinierte Formatierung](../../../docs/standard/base-types/composite-formatting.md)
