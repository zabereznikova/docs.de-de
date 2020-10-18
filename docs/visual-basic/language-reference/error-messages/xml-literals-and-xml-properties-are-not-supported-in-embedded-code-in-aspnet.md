---
title: XML-Literale und XML-Eigenschaften werden in eingebettetem Code in ASP.NET nicht unterstützt
ms.date: 07/20/2015
f1_keywords:
- vbc31200
- bc31200
helpviewer_keywords:
- BC31200
ms.assetid: 053e8cba-8584-45cc-9fa0-43d122779772
ms.openlocfilehash: d96386f8495685391203826fea85efba47c44951
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "92163258"
---
# <a name="bc31200-xml-literals-and-xml-properties-are-not-supported-in-embedded-code-within-aspnet"></a>BC31200: XML-Literale und XML-Eigenschaften werden in eingebettetem Code in ASP.net nicht unterstützt.

XML-Literale und XML-Eigenschaften werden in eingebettetem Code in ASP.net nicht unterstützt. Wenn Sie XML-Funktionen verwenden möchten, verschieben Sie den Code in Code Behind.

 XML-Literale oder XML-Achsen Eigenschaften werden in eingebettetem Code ( `<%= =>` ) in einer ASP.NET-Datei definiert.

 **Fehler-ID:** BC31200

## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler

- Verschieben Sie den Code, der die XML-Literale oder XML-Achsen Eigenschaft enthält, in eine ASP.NET-Code Behind-Datei.

## <a name="see-also"></a>Siehe auch

- [XML-Literale](../xml-literals/index.md)
- [XML-Achseneigenschaften](../xml-axis/index.md)
- [XML](../../programming-guide/language-features/xml/index.md)
