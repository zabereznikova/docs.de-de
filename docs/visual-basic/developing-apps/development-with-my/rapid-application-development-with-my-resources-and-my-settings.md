---
title: Schnelle Anwendungsentwicklung mit My.Resources und My.Settings
ms.date: 07/20/2015
helpviewer_keywords:
- My.Settings object [Visual Basic], developing applications
- rapid application development (RAD), My.Resources
- rapid application development (RAD), My.Settings
- My.Resources object [Visual Basic], developing applications
ms.assetid: 68284ab1-b685-4814-a2a4-01ae40445ff8
ms.openlocfilehash: ce9a5bf76ba3132f58aa40227a145d8b5bf1591d
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349265"
---
# <a name="rapid-application-development-with-myresources-and-mysettings-visual-basic"></a>Schnelle Anwendungsentwicklung mit My.Resources und My.Settings (Visual Basic)

Das `My.Resources`-Objekt ermöglicht den Zugriff auf die Ressourcen der Anwendung und ermöglicht das dynamische Abrufen von Ressourcen für Ihre Anwendung.  
  
## <a name="retrieving-resources"></a>Abrufen von Ressourcen  

 Eine Reihe von Ressourcen, z. b. Audiodateien, Symbole, Bilder und Zeichen folgen, können über das `My.Resources` Objekt abgerufen werden. Beispielsweise können Sie auf die kulturspezifischen Ressourcen Dateien der Anwendung zugreifen. Im folgenden Beispiel wird das Symbol des Formulars auf das Symbol `Form1Icon` festgelegt, das in der Ressourcen Datei der Anwendung gespeichert ist.  
  
 [!code-vb[VbVbcnMy#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMy/VB/Class1.vb#7)]  
  
 Das `My.Resources`-Objekt macht nur globale Ressourcen verfügbar. Er bietet keinen Zugriff auf Ressourcen Dateien, die Formularen zugeordnet sind. Sie müssen über das Formular auf die Formular Ressourcen zugreifen.  
  
 Ebenso bietet das `My.Settings`-Objektzugriff auf die Einstellungen der Anwendung und ermöglicht das dynamische Speichern und Abrufen von Eigenschafts Einstellungen und anderen Informationen für Ihre Anwendung. Weitere Informationen finden Sie unter [My. Resources-Objekt](../../../visual-basic/language-reference/objects/my-resources-object.md) und [My. Settings-Objekt](../../../visual-basic/language-reference/objects/my-settings-object.md).  
  
## <a name="see-also"></a>Siehe auch

- [My.Resources-Objekt](../../../visual-basic/language-reference/objects/my-resources-object.md)
- [My.Settings-Objekt](../../../visual-basic/language-reference/objects/my-settings-object.md)
- [Accessing Application Settings](../../../visual-basic/developing-apps/programming/app-settings/index.md)
