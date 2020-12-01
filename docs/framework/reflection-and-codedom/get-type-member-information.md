---
title: 'Vorgehensweise: Abrufen von Typ- und Memberinformationen mithilfe von Reflektion'
description: Hier erfahren Sie, wie Sie mit der Reflexion mithilfe des System.Reflection-Namespace Informationen zum Typ und Member erhalten.
ms.date: 09/03/2019
helpviewer_keywords:
- reflection, obtaining member information
- types [.NET Framework], obtaining member information from
ms.assetid: 348ae651-ccda-4f13-8eda-19e8337e9438
dev_langs:
- cpp
- csharp
- vb
ms.openlocfilehash: 771917bb2ae5cae56c775ae23119d5eda9701df1
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96266323"
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
