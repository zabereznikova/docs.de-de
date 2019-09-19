---
title: 'Vorgehensweise: Abrufen von Typ- und Memberinformationen mithilfe von Reflektion'
ms.date: 09/03/2019
helpviewer_keywords:
- reflection, obtaining member information
- types [.NET Framework], obtaining member information from
ms.assetid: 348ae651-ccda-4f13-8eda-19e8337e9438
author: rpetrusha
ms.author: ronpet
dev_langs:
- cpp
- csharp
- vb
ms.openlocfilehash: da71845ea276267220636cfd661465ea02b2b50d
ms.sourcegitcommit: 7b1ce327e8c84f115f007be4728d29a89efe11ef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/13/2019
ms.locfileid: "70972858"
---
# <a name="how-to-get-type-and-member-information-by-using-reflection"></a>Vorgehensweise: Abrufen von Typ- und Memberinformationen mithilfe von Reflektion
Der <xref:System.Reflection>-Namespace enthält viele Methoden zum Abrufen von Informationen zu Typen und deren Membern. In diesem Artikel wird eine dieser Methoden, nämlich <xref:System.Type.GetMembers%2A?displayProperty=nameWithType>, veranschaulicht. Weitere Informationen finden Sie unter [Übersicht über Reflektion](reflection.md).
  
## <a name="example"></a>Beispiel

In folgendem Beispiel werden mithilfe von Reflektion Typ- und Memberinformationen aus einer Assembly abgerufen:

[!code-cpp[Get type members](../../../samples/snippets/standard/reflection/memberinfo/gettypemembers.cpp)]
[!code-csharp[Get type members](../../../samples/snippets/standard/reflection/memberinfo/gettypemembers.cs)]
[!code-vb[Get type members](../../../samples/snippets/standard/reflection/memberinfo/gettypemembers.vb)]

## <a name="see-also"></a>Siehe auch

- [Programmieren mit Anwendungsdomänen](../app-domains/application-domains.md#programming-with-application-domains)
- [Reflexion](reflection.md)
- [Verwenden von Anwendungsdomänen](../app-domains/use.md)
