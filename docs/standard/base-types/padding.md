---
title: "Auffüllen von Zeichenfolgen in .NET"
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
- cpp
helpviewer_keywords:
- strings [.NET Framework], padding
- white space
- PadRight method
- PadLeft method
- padding strings
ms.assetid: 84a9f142-3244-4c90-ba02-21af9bbaff71
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 29cd40645cf06ac9babb4738259938a3da04a155
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="padding-strings-in-net"></a>Auffüllen von Zeichenfolgen in .NET
Verwenden Sie eine der folgenden <xref:System.String> Methoden zum Erstellen einer neuen Zeichenfolge, die der ursprünglichen Zeichenfolge, die aufgefüllt wird besteht, mit führenden oder nachgestellten Zeichen auf eine angegebene Gesamtlänge zu erreichen. Als Auffüllzeichen können Leerzeichen oder ein angegebenes Zeichen verwendet werden, sodass die Zeichenfolge entweder rechtsbündig oder linksbündig ausgerichtet angezeigt wird.  
  
|Methodenname|Verwendung|  
|-----------------|---------|  
|<xref:System.String.PadLeft%2A?displayProperty=nameWithType>|Füllt eine Zeichenfolge mit vorangestellten Zeichen auf, um eine angegebene Gesamtlänge zu erreichen.|  
|<xref:System.String.PadRight%2A?displayProperty=nameWithType>|Füllt eine Zeichenfolge mit nachgestellten Zeichen auf, um eine angegebene Gesamtlänge zu erreichen.|  
  
## <a name="padleft"></a>PadLeft  
 Die <xref:System.String.PadLeft%2A?displayProperty=nameWithType> Methode erstellt eine neue Zeichenfolge durch Verketten genügend führende Auffüllzeichen mit der ursprünglichen Zeichenfolge um eine angegebene Gesamtlänge zu erreichen. Die <xref:System.String.PadLeft%28System.Int32%29?displayProperty=nameWithType> Methode Leerzeichen als Auffüllzeichen verwendet und die <xref:System.String.PadLeft%28System.Int32%2CSystem.Char%29?displayProperty=nameWithType> Methode können Sie eigene Auffüllzeichen angeben.  
  
 Im folgenden Codebeispiel wird mit der <xref:System.String.PadLeft%2A> Methode zum Erstellen einer neuen Zeichenfolge, die 20 Zeichen lang ist. In diesem Beispiel wird „`--------Hello World!`“ auf der Konsole angezeigt.  
  
 [!code-cpp[Conceptual.String.BasicOps#3](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.basicops/cpp/padding.cpp#3)]
 [!code-csharp[Conceptual.String.BasicOps#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/padding.cs#3)]
 [!code-vb[Conceptual.String.BasicOps#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/padding.vb#3)]  
  
## <a name="padright"></a>PadRight  
 Die <xref:System.String.PadRight%2A?displayProperty=nameWithType> Methode erstellt eine neue Zeichenfolge durch Verketten genügend nachgestellte Auffüllzeichen mit der ursprünglichen Zeichenfolge um eine angegebene Gesamtlänge zu erreichen. Die <xref:System.String.PadRight%28System.Int32%29?displayProperty=nameWithType> Methode Leerzeichen als Auffüllzeichen verwendet und die <xref:System.String.PadRight%28System.Int32%2CSystem.Char%29?displayProperty=nameWithType> Methode können Sie eigene Auffüllzeichen angeben.  
  
 Im folgenden Codebeispiel wird mit der <xref:System.String.PadRight%2A> Methode zum Erstellen einer neuen Zeichenfolge, die 20 Zeichen lang ist. In diesem Beispiel wird „`Hello World!--------`“ auf der Konsole angezeigt.  
  
 [!code-cpp[Conceptual.String.BasicOps#4](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.basicops/cpp/padding.cpp#4)]
 [!code-csharp[Conceptual.String.BasicOps#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/padding.cs#4)]
 [!code-vb[Conceptual.String.BasicOps#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/padding.vb#4)]  
  
## <a name="see-also"></a>Siehe auch  
 [Grundlegende Zeichenfolgenoperationen](../../../docs/standard/base-types/basic-string-operations.md)
