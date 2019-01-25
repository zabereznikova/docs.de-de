---
title: Schnelle Anwendungsentwicklung mit My.Resources und My.Settings (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- My.Settings object [Visual Basic], developing applications
- rapid application development (RAD), My.Resources
- rapid application development (RAD), My.Settings
- My.Resources object [Visual Basic], developing applications
ms.assetid: 68284ab1-b685-4814-a2a4-01ae40445ff8
ms.openlocfilehash: 4150d2f9634045351cb52e02c4f4807e55d118e6
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54717899"
---
# <a name="rapid-application-development-with-myresources-and-mysettings-visual-basic"></a>Schnelle Anwendungsentwicklung mit My.Resources und My.Settings (Visual Basic)
Die `My.Resources` Objekt bietet Zugriff auf die Ressourcen der Anwendung und ermöglicht es Ihnen, Ressourcen für Ihre Anwendung dynamisch abzurufen.  
  
## <a name="retrieving-resources"></a>Abrufen von Ressourcen  
 Eine Reihe von Ressourcen wie Audiodateien, Symbole, Bilder und Zeichenfolgen abgerufen werden kann, über die `My.Resources` Objekt. Beispielsweise können Sie die Dateien der Anwendung kulturspezifische Ressource zugreifen. Im folgenden Beispiel wird das Symbol für das Formular auf das Symbol mit dem Namen `Form1Icon` in der Ressourcendatei der Anwendung gespeichert.  
  
 [!code-vb[VbVbcnMy#7](../../../visual-basic/developing-apps/development-with-my/codesnippet/VisualBasic/rapid-application-development-with-my-resources-and-my-settings_1.vb)]  
  
 Die `My.Resources` -Objekt macht nur globale Ressourcen verfügbar. Er bietet Zugriff auf die Ressourcendateien, die Formularen zugeordnet. Sie müssen die Formularressourcen aus dem Formular zugreifen.  
  
 Auf ähnliche Weise die `My.Settings` Objekt bietet Zugriff auf die Einstellungen der Anwendung und ermöglicht es Ihnen, dynamisch speichern und Abrufen von Eigenschaften und andere Informationen für Ihre Anwendung. Weitere Informationen finden Sie unter [My.Resources-Objekt](../../../visual-basic/language-reference/objects/my-resources-object.md) und [My.Settings-Objekt](../../../visual-basic/language-reference/objects/my-settings-object.md).  
  
## <a name="see-also"></a>Siehe auch
- [My.Resources-Objekt](../../../visual-basic/language-reference/objects/my-resources-object.md)
- [My.Settings-Objekt](../../../visual-basic/language-reference/objects/my-settings-object.md)
- [Zugreifen auf Anwendungseinstellungen](../../../visual-basic/developing-apps/programming/app-settings/index.md)
