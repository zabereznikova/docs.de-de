---
title: Enumerationsformatzeichenfolgen
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
- format specifiers, enumeration format strings
- enumeration format strings
- formatting [.NET Framework], enumeration
ms.assetid: dd1ff672-1052-42cf-8666-4924fb6cd1a1
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 58004fa19f2ec3b1ca7570d6ca75702510148002
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/23/2017
---
# <a name="enumeration-format-strings"></a>Enumerationsformatzeichenfolgen
Sie können die <xref:System.Enum.ToString%2A?displayProperty=nameWithType>-Methode verwenden, um ein neues Zeichenfolgenobjekt zu erstellen, das den numerischen, den Hexadezimal- oder den Zeichenfolgenwert eines Enumerationsmembers darstellt. Diese Methode akzeptiert eine der Enumerationsformatzeichenfolgen, um den Wert anzugeben, der zurückgegeben werden soll.  
  
 In der folgenden Tabelle sind die Enumerationsformatzeichenfolgen sowie die Werte aufgeführt, die diese zurückgeben. Bei diesen Formatbezeichnern wird die Groß- und Kleinschreibung nicht berücksichtigt.  
  
| Formatierungszeichenfolge | Ergebnis |  
| ------------- | ------ |  
| G oder g | Zeigt den Enumerationseintrag nach Möglichkeit als Zeichenfolgenwert an, zeigt andernfalls den ganzzahligen Wert der aktuellen Instanz an. Wenn die Enumeration mit festgelegtem **Flags**-Attribut definiert ist, werden die Zeichenfolgenwerte jedes gültigen Eintrags miteinander verkettet und durch Kommas getrennt. Wenn das **Flags**-Attribut nicht festgelegt ist, wird ein ungültiger Wert als numerischer Eintrag angezeigt. Das folgende Beispiel veranschaulicht den Formatbezeichner „G“.<br><br>[!code-csharp[Formatting.Enum#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.Enum/cs/enum1.cs#1)] [!code-vb[Formatting.Enum#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Enum/vb/enum1.vb#1)] |  
| F oder f | Zeigt den Enumerationseintrag nach Möglichkeit als Zeichenfolgenwert an. Wenn der Wert vollständig als Summe der Einträge in der Enumeration angezeigt werden kann (selbst wenn das **Flags**-Attribut nicht vorhanden ist), werden die Zeichenfolgenwerte jedes gültigen Eintrags miteinander verkettet und durch Kommas getrennt. Wenn der Wert nicht vollständig durch die Enumerationseinträge ermittelt werden kann, wird der Wert als ganzzahliger Wert formatiert. Das folgende Beispiel veranschaulicht den Formatbezeichner „F“.<br><br>[!code-csharp[Formatting.Enum#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.Enum/cs/enum1.cs#2)] [!code-vb[Formatting.Enum#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Enum/vb/enum1.vb#2)] |  
| D oder d | Zeigt den Enumerationseintrag in der kürzestmöglichen Darstellung als ganzzahligen Wert an. Das folgende Beispiel veranschaulicht den Formatbezeichner „D“.<br><br>[!code-csharp[Formatting.Enum#3](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.Enum/cs/enum1.cs#3)] [!code-vb[Formatting.Enum#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Enum/vb/enum1.vb#3)] |  
| X oder x | Zeigt den Enumerationseintrag als Hexadezimalwert an. Der Wert wird mit so vielen führenden Nullen wie nötig dargestellt, um sicherzustellen, dass der Wert mindestens acht Stellen lang ist. Das folgende Beispiel veranschaulicht den Formatbezeichner „X“.<br /><br /> [!code-csharp[Formatting.Enum#4](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.Enum/cs/enum1.cs#4)] [!code-vb[Formatting.Enum#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Enum/vb/enum1.vb#4)] |  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel definiert eine Enumeration namens `Colors`, die aus drei Einträgen besteht: `Red`, `Blue` und `Green`.  
  
 [!code-csharp[Formatting.Enum#5](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.Enum/cs/enum1.cs#5)]
 [!code-vb[Formatting.Enum#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Enum/vb/enum1.vb#5)]  
  
 Nachdem die Enumeration definiert wurde, kann auf folgende Weise eine Instanz deklariert werden.  
  
 [!code-csharp[Formatting.Enum#6](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.Enum/cs/enum1.cs#6)]
 [!code-vb[Formatting.Enum#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Enum/vb/enum1.vb#6)]  
  
 Dann kann die `Color.ToString(System.String)`-Methode verwendet werden, um den Enumerationswert je nach übergebenem Formatbezeichner auf verschiedene Arten anzuzeigen.  
  
 [!code-csharp[Formatting.Enum#7](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.Enum/cs/enum1.cs#7)]
 [!code-vb[Formatting.Enum#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Enum/vb/enum1.vb#7)]  
  
## <a name="see-also"></a>Siehe auch  
 [Formatierung von Typen](../../../docs/standard/base-types/formatting-types.md)
