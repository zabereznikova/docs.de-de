---
title: 'Vorgehensweise: Abrufen von Typ- und Memberinformationen aus einer Assembly'
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
ms.openlocfilehash: 9f9d01715a9635b276ca87d94082bb4d3820084e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59138878"
---
# <a name="how-to-obtain-type-and-member-information-from-an-assembly"></a>Vorgehensweise: Abrufen von Typ- und Memberinformationen aus einer Assembly
Der <xref:System.Reflection>-Namespace enthält viele Methoden zum Abrufen von Informationen aus einer Assembly. In diesem Abschnitt wird eine dieser Methoden veranschaulicht. Weitere Informationen finden Sie unter [Reflection Overview (Übersicht über Reflektion)](../../../docs/framework/reflection-and-codedom/reflection.md).  
  
 In folgendem Beispiel werden Typ- und Memberinformationen aus einer Assembly abgerufen.  
  
## <a name="example"></a>Beispiel  
 [!code-cpp[Conceptual.Types.ViewInfo#8](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.types.viewinfo/cpp/source6.cpp#8)]
 [!code-csharp[Conceptual.Types.ViewInfo#8](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.types.viewinfo/cs/source6.cs#8)]
 [!code-vb[Conceptual.Types.ViewInfo#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.types.viewinfo/vb/source6.vb#8)]  
  
## <a name="see-also"></a>Siehe auch

- [Programming with Application Domains (Programmieren mit Anwendungsdomänen)](./application-domains.md#programming-with-application-domains)
- [Reflexion](../../../docs/framework/reflection-and-codedom/reflection.md)
- [Verwenden von Anwendungsdomänen](../../../docs/framework/app-domains/use.md)
