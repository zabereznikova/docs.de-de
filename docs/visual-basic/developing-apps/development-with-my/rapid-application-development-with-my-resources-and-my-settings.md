---
title: Schnelle Anwendungsentwicklung mit My.Resources und My.Settings (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- My.Settings object [Visual Basic], developing applications
- rapid application development (RAD), My.Resources
- rapid application development (RAD), My.Settings
- My.Resources object [Visual Basic], developing applications
ms.assetid: 68284ab1-b685-4814-a2a4-01ae40445ff8
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 1657febf935560ff4c8dd2f54b10fdcb2254891f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="rapid-application-development-with-myresources-and-mysettings-visual-basic"></a>Schnelle Anwendungsentwicklung mit My.Resources und My.Settings (Visual Basic)
Die `My.Resources` -Objekt ermöglicht den Zugriff auf die Ressourcen der Anwendung und ermöglicht Ihnen, Ressourcen für Ihre Anwendung dynamisch abzurufen.  
  
## <a name="retrieving-resources"></a>Abrufen von Ressourcen  
 Eine Reihe von Ressourcen wie Audiodateien, Symbole, Bilder und Zeichenfolgen abgerufen werden kann, über die `My.Resources` Objekt. Beispielsweise können Sie die Anwendung kulturspezifische Ressourcendateien zugreifen. Im folgenden Beispiel wird das Symbol des Formulars auf das Symbol mit dem Namen `Form1Icon` in der Anwendung Ressourcendatei gespeichert.  
  
 [!code-vb[VbVbcnMy#7](../../../visual-basic/developing-apps/development-with-my/codesnippet/VisualBasic/rapid-application-development-with-my-resources-and-my-settings_1.vb)]  
  
 Die `My.Resources` Objekt macht nur globale Ressourcen verfügbar. Es stellt nicht den Zugriff auf Formularen zugeordnete Ressourcendateien bereit. Sie müssen die Formularressourcen aus dem Formular zugreifen. Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Lokalisieren von Windows Forms](http://msdn.microsoft.com/en-us/9a96220d-a19b-4de0-9f48-01e5d82679e5).  
  
 Auf ähnliche Weise die `My.Settings` Objekt ermöglicht den Zugriff auf die Einstellungen der Anwendung, und lassen sich dynamisch speichern und Abrufen von Einstellungen und andere Informationen für Ihre Anwendung. Weitere Informationen finden Sie unter [My.Resources-Objekt](../../../visual-basic/language-reference/objects/my-resources-object.md) und [My.Settings-Objekt](../../../visual-basic/language-reference/objects/my-settings-object.md).  
  
## <a name="see-also"></a>Siehe auch  
 [My.Resources-Objekt](../../../visual-basic/language-reference/objects/my-resources-object.md)  
 [My.Settings-Objekt](../../../visual-basic/language-reference/objects/my-settings-object.md)  
 [Zugreifen auf Anwendungseinstellungen](../../../visual-basic/developing-apps/programming/app-settings/accessing-application-settings.md)
