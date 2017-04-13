---
title: "Auff&#252;llen von Zeichenfolgen in .NET Framework | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Auffüllen von Zeichenfolgen"
  - "PadLeft-Methode"
  - "PadRight-Methode"
  - "Zeichenfolgen [.NET Framework], Abstand"
  - "Leerraum"
ms.assetid: 84a9f142-3244-4c90-ba02-21af9bbaff71
caps.latest.revision: 12
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 12
---
# Auff&#252;llen von Zeichenfolgen in .NET Framework
Mit einer der folgenden <xref:System.String>\-Methoden können Sie eine neue Zeichenfolge erstellen, die aus einer ursprünglichen Zeichenfolge sowie den führenden und nachgestellten Zeichen besteht, mit denen diese auf eine angegebene Gesamtlänge aufgefüllt wurde.  Als Auffüllzeichen können Leerzeichen oder ein angegebenes Zeichen verwendet werden. Es wird rechts\- oder linksbündig dargestellt.  
  
|Methodenname|Verwendung|  
|------------------|----------------|  
|<xref:System.String.PadLeft%2A?displayProperty=fullName>|Füllt eine Zeichenfolge mit führenden Zeichen auf die angegebene Gesamtlänge auf.|  
|<xref:System.String.PadRight%2A?displayProperty=fullName>|Füllt eine Zeichenfolge mit nachgestellten Zeichen auf die angegebene Gesamtlänge auf.|  
  
## PadLeft  
 Die <xref:System.String.PadLeft%2A?displayProperty=fullName>\-Methode erstellt eine neue Zeichenfolge, indem sie genügend führende Auffüllzeichen mit der ursprünglichen Zeichenfolge verkettet, um die angegebene Gesamtlänge zu erreichen.  Bei der <xref:System.String.PadLeft%28System.Int32%29?displayProperty=fullName>\-Methode wird das Leerzeichen als Auffüllzeichen verwendet. Für die <xref:System.String.PadLeft%28System.Int32%2CSystem.Char%29?displayProperty=fullName>\-Methode können Sie ein eigenes Auffüllzeichen angeben.  
  
 Im folgenden Codebeispiel wird mithilfe der <xref:System.String.PadLeft%2A>\-Methode eine Zeichenfolge erstellt, die 20 Zeichen lang ist.  Auf der Konsole wird dann "`--------Hello World!`" angezeigt.  
  
 [!code-cpp[Conceptual.String.BasicOps#3](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.basicops/cpp/padding.cpp#3)]
 [!code-csharp[Conceptual.String.BasicOps#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/padding.cs#3)]
 [!code-vb[Conceptual.String.BasicOps#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/padding.vb#3)]  
  
## PadRight  
 Die <xref:System.String.PadRight%2A?displayProperty=fullName>\-Methode erstellt eine neue Zeichenfolge, indem sie genügend nachgestellte Auffüllzeichen mit der ursprünglichen Zeichenfolge verkettet, um die angegebene Gesamtlänge zu erreichen.  Bei der <xref:System.String.PadRight%28System.Int32%29?displayProperty=fullName>\-Methode wird das Leerzeichen als Auffüllzeichen verwendet. Für die <xref:System.String.PadRight%28System.Int32%2CSystem.Char%29?displayProperty=fullName>\-Methode können Sie ein eigenes Auffüllzeichen angeben.  
  
 Im folgenden Codebeispiel wird mithilfe der <xref:System.String.PadRight%2A>\-Methode eine neue Zeichenfolge erstellt, die 20 Zeichen lang ist.  Auf der Konsole wird dann "`Hello World!--------`" angezeigt.  
  
 [!code-cpp[Conceptual.String.BasicOps#4](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.basicops/cpp/padding.cpp#4)]
 [!code-csharp[Conceptual.String.BasicOps#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/padding.cs#4)]
 [!code-vb[Conceptual.String.BasicOps#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/padding.vb#4)]  
  
## Siehe auch  
 [Grundlegende Zeichenfolgenoperationen](../../../docs/standard/base-types/basic-string-operations.md)