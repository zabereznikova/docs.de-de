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
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349265"
---
# <a name="rapid-application-development-with-myresources-and-mysettings-visual-basic"></a>Schnelle Anwendungsentwicklung mit My.Resources und My.Settings (Visual Basic)

Mit dem Objekt `My.Resources` erhalten Sie Zugriff auf die Anwendungsressourcen und können Ressourcen für Ihre Anwendung dynamisch abrufen.  
  
## <a name="retrieving-resources"></a>Abrufen von Ressourcen  

 Mithilfe des `My.Resources`-Objekts können Sie eine Reihe von Ressourcen abrufen, wie etwa Audiodateien, Symbole, Bilder und Zeichenfolgen. Sie können beispielsweise auf die kulturspezifischen Ressourcendateien der Anwendung zugreifen. Im folgenden Beispiel wird das Symbol des Formulars auf das Symbol `Form1Icon` festgelegt, das in der Ressourcendatei der Anwendung gespeichert ist.  
  
 [!code-vb[VbVbcnMy#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMy/VB/Class1.vb#7)]  
  
 Das `My.Resources`-Objekt macht nur globale Ressourcen verfügbar. Es bietet keinen Zugriff auf Ressourcendateien, die Formularen zugeordnet sind. Zugriff auf die Formularressourcen erhalten Sie über das Formular.  
  
 Ebenso bietet das `My.Settings`-Objekt Zugriff auf die Einstellungen der Anwendung und ermöglicht das dynamische Speichern und Abrufen von Eigenschafteneinstellungen und anderen Informationen für Ihre Anwendung. Weitere Informationen finden Sie unter [My.Resources-Objekt](../../../visual-basic/language-reference/objects/my-resources-object.md) und [My.Settings-Objekt](../../../visual-basic/language-reference/objects/my-settings-object.md).  
  
## <a name="see-also"></a>Siehe auch

- [My.Resources-Objekt](../../../visual-basic/language-reference/objects/my-resources-object.md)
- [My.Settings-Objekt](../../../visual-basic/language-reference/objects/my-settings-object.md)
- [Zugreifen auf Anwendungseinstellungen](../../../visual-basic/developing-apps/programming/app-settings/index.md)
