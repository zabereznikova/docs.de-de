---
title: Von My.Forms und My.WebServices bereitgestellte Standardobjektinstanzen (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- My.WebServices object [Visual Basic], developing applications
- My.Forms object [Visual Basic], developing applications
- rapid application development (RAD), My.Forms
- rapid application development (RAD), My.WebServices
ms.assetid: de930027-9108-4f0c-b97c-5e7db4d6ef79
ms.openlocfilehash: 9285e88e3dc9fd8b3731416b1c40811188d6a33d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54563599"
---
# <a name="default-object-instances-provided-by-myforms-and-mywebservices-visual-basic"></a>Von My.Forms und My.WebServices bereitgestellte Standardobjektinstanzen (Visual Basic)
Die [My.Forms](../../../visual-basic/language-reference/objects/my-forms-object.md) und [My.WebServices](../../../visual-basic/language-reference/objects/my-webservices-object.md) Objekte bieten Zugriff auf Formulare, Datenquellen und XML-Webdienste, die von der Anwendung verwendet. Dies erfolgt durch Bereitstellen von Sammlungen von *Standardinstanzen* jedes dieser Objekte.  
  
## <a name="default-instances"></a>Standard-Instanzen  
 Eine Standardinstanz ist eine Instanz der Klasse, die von der Laufzeit bereitgestellt wird, und muss nicht werden deklariert und instanziiert wird, mit der `Dim` und `New` Anweisungen. Das folgende Beispiel zeigt, wie Sie möglicherweise haben deklariert und instanziiert eine Instanz von einer <xref:System.Windows.Forms.Form> Klasse mit dem Namen `Form1`, und wie Sie jetzt erhalten Sie eine Standardinstanz dieser <xref:System.Windows.Forms.Form> -Klasse über `My.Forms`.  
  
 [!code-vb[VbVbcnMy#5](../../../visual-basic/developing-apps/development-with-my/codesnippet/VisualBasic/default-object-instances-provided-by-my-forms-and-my-webservices_1.vb)]  
  
 [!code-vb[VbVbcnMy#6](../../../visual-basic/developing-apps/development-with-my/codesnippet/VisualBasic/default-object-instances-provided-by-my-forms-and-my-webservices_2.vb)]  
  
 Die `My.Forms` -Objekt gibt eine Auflistung der Standardinstanzen für jede `Form` -Klasse, die in Ihrem Projekt vorhanden ist. Auf ähnliche Weise `My.WebServices` bietet Sie einer Standardinstanz der Proxyklasse für jeden Webdienst, dass Sie einen Verweis auf in Ihrer Anwendung erstellt haben.  
  
## <a name="see-also"></a>Siehe auch
- [My.Forms-Objekt](../../../visual-basic/language-reference/objects/my-forms-object.md)
- [My.WebServices-Objekt](../../../visual-basic/language-reference/objects/my-webservices-object.md)
- [Merkmale von "My" auf Grundlage des Projekttyps](../../../visual-basic/developing-apps/development-with-my/how-my-depends-on-project-type.md)
