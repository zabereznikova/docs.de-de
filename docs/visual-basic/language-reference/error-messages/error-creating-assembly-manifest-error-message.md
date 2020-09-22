---
title: 'Fehler beim Erstellen des Assemblymanifests: <error message>'
ms.date: 07/20/2015
f1_keywords:
- bc30140
- vbc30140
helpviewer_keywords:
- BC30140
ms.assetid: 1beb5aa0-7b79-4c85-946b-5c2d0a41d1d2
ms.openlocfilehash: e90ad1905123a3c5426ada15e21179abe5c078ab
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90874409"
---
# <a name="error-creating-assembly-manifest-error-message"></a>Fehler beim Erstellen des Assemblymanifests: \<error message>

Der Visual Basic-Compiler ruft den Assemblylinker (Al.exe, auch bekannt als ALink) auf, um eine Assembly mit einem Manifest zu generieren. Der Linker meldet einen Fehler in der Vorausgabestufe der Assemblyerstellung.  
  
 Zu diesem Fehler kann es kommen, wenn es Probleme mit der angegebenen Schlüsseldatei oder dem angegebenen Schlüsselcontainer gibt. Um eine Assembly vollständig zu signieren, müssen Sie eine gültige Schlüsseldatei bereitstellen, die Informationen zu den öffentlichen und privaten Schlüsseln enthält. Um das Signieren einer Assembly zu verzögern, müssen Sie das Kontrollkästchen **Nur verzögerte Signierung** aktivieren und eine gültige Schlüsseldatei angeben, die Informationen zum öffentlichen Schlüssel enthält. Der private Schlüssel ist nicht erforderlich, wenn eine Assembly verzögert signiert wird. Weitere Informationen finden Sie unter [Vorgehensweise: Signieren einer Assembly mit einem starken Namen](../../../standard/assembly/sign-strong-name.md).  
  
 **Fehler-ID:** BC30140  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1. Überprüfen Sie die Fehlermeldung in Anführungszeichen, und lesen Sie das Thema [Al.exe](../../../framework/tools/al-exe-assembly-linker.md) Fehler AL1019 weitere Erläuterung und Ratschläge  
  
2. Wenn der Fehler weiterhin besteht, tragen Sie Informationen zu den Umständen zusammen, und benachrichtigen Sie den Produktsupport von Microsoft.  
  
## <a name="see-also"></a>Weitere Informationen

- [How to: Signieren einer Assembly mit einem starken Namen](../../../standard/assembly/sign-strong-name.md)
- [Seite "Signierung", Projekt-Designer](/visualstudio/ide/reference/signing-page-project-designer)
- [Al.exe](../../../framework/tools/al-exe-assembly-linker.md)
- [Sprechen Sie mit uns](/visualstudio/ide/feedback-options)
