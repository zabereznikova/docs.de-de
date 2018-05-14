---
title: 'Gewusst wie: Abrufen von Typ- und Memberinformationen aus einer Assembly'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- obtaining assembly information
- assemblies [.NET Framework], obtaining information from
ms.assetid: 348ae651-ccda-4f13-8eda-19e8337e9438
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5fb06555f18c13f87347a5a76e6f4a3060777f02
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="how-to-obtain-type-and-member-information-from-an-assembly"></a>Gewusst wie: Abrufen von Typ- und Memberinformationen aus einer Assembly
Der <xref:System.Reflection>-Namespace enthält viele Methoden zum Abrufen von Informationen aus einer Assembly. In diesem Abschnitt wird eine dieser Methoden veranschaulicht. Weitere Informationen finden Sie unter [Reflection Overview (Übersicht über Reflektion)](../../../docs/framework/reflection-and-codedom/reflection.md).  
  
 In folgendem Beispiel werden Typ- und Memberinformationen aus einer Assembly abgerufen.  
  
## <a name="example"></a>Beispiel  
 [!code-cpp[Conceptual.Types.ViewInfo#8](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.types.viewinfo/cpp/source6.cpp#8)]
 [!code-csharp[Conceptual.Types.ViewInfo#8](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.types.viewinfo/cs/source6.cs#8)]
 [!code-vb[Conceptual.Types.ViewInfo#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.types.viewinfo/vb/source6.vb#8)]  
  
## <a name="see-also"></a>Siehe auch  
 [Programming with Application Domains (Programmieren mit Anwendungsdomänen)](./application-domains.md#programming-with-application-domains) [Reflektion](../../../docs/framework/reflection-and-codedom/reflection.md)  
 [Verwenden von Anwendungsdomänen](../../../docs/framework/app-domains/use.md)
