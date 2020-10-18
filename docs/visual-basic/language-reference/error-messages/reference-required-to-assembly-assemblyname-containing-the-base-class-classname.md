---
title: Es ist ein Verweis auf die Assembly "<assemblyname>" erforderlich, die die Basisklasse "<classname>" enthält.
ms.date: 07/20/2015
f1_keywords:
- bc30007
- vbc30007
helpviewer_keywords:
- BC30007
ms.assetid: 5f34cf47-6c6e-4954-bd8e-d6b020b75fb7
ms.openlocfilehash: d2fb3498219dfe3318ec418ede250de818874ba9
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "92162335"
---
# <a name="bc30007-reference-required-to-assembly-assemblyname-containing-the-base-class-classname"></a>BC30007: Es ist ein Verweis auf die Assembly "" erforderlich, \<assemblyname> die die Basisklasse " \<classname> " enthält

Es ist ein Verweis auf die Assembly "" erforderlich, \<assemblyname> die die Basisklasse "" enthält \<classname> . Fügen Sie dem Projekt einen Verweis hinzu.

 Die Klasse ist in einer Dynamic Link Library (DLL) oder Assembly definiert, auf die in Ihrem Projekt nicht direkt verwiesen wird. Der Visual Basic-Compiler benötigt einen Verweis, um Mehrdeutigkeiten zu vermeiden, falls die Klasse in mehr als einer DLL oder Assembly definiert ist.

 **Fehler-ID:** BC30007

## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler

- Nehmen Sie den Namen der nicht referenzierten DLL oder Assembly in Ihre Projektverweise auf.

## <a name="see-also"></a>Siehe auch

- [Verwalten von Verweisen in einem Projekt](/visualstudio/ide/managing-references-in-a-project)
- [Problembehandlung bei fehlerhaften Verweisen](/visualstudio/ide/troubleshooting-broken-references)
