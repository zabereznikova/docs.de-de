---
title: XML-Namespace-URI ''<uri>'' kann nur an ''xmlns'' gebunden werden
ms.date: 07/20/2015
f1_keywords:
- bc31183
- vbc31183
helpviewer_keywords:
- BC31183
ms.assetid: 0ab1dbce-8397-4959-b2cd-f58798b051a0
ms.openlocfilehash: 1aec6ac0a354bfe7e0378a2e46a70a7161bf6d36
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "92163245"
---
# <a name="bc31183-xml-namespace-uri-httpwwww3orgxml1998namespace-can-be-bound-only-to-xmlns"></a>BC31183: XML-Namespace-URI `http://www.w3.org/XML/1998/namespace` ; kann nur an ' xmlns ' gebunden werden.

Der URI `http://www.w3.org/XML/1998/namespace` wird in einer XML-Namespace Deklaration verwendet. Dieser URI ist ein reservierter Namespace und kann nicht in einer XML-Namespace Deklaration enthalten sein.

 **Fehler-ID:** BC31183

## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler

Entfernen Sie die XML-Namespace Deklaration, oder ersetzen Sie den URI `http://www.w3.org/XML/1998/namespace` durch einen gültigen Namespace-URI.

## <a name="see-also"></a>Siehe auch

- [Imports-Anweisung (XML-Namespace)](../statements/imports-statement-xml-namespace.md)
- [XML-Literale](../xml-literals/index.md)
- [XML](../../programming-guide/language-features/xml/index.md)
