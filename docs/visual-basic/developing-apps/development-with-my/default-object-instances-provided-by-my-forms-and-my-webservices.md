---
title: Von My.Forms und My.WebServices bereitgestellte Standardobjektinstanzen (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- My.WebServices object [Visual Basic], developing applications
- My.Forms object [Visual Basic], developing applications
- rapid application development (RAD), My.Forms
- rapid application development (RAD), My.WebServices
ms.assetid: de930027-9108-4f0c-b97c-5e7db4d6ef79
ms.openlocfilehash: ca31e1c40c77bf7f42d246019d81f4ffaed646e8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62014452"
---
# <a name="default-object-instances-provided-by-myforms-and-mywebservices-visual-basic"></a>Von My.Forms und My.WebServices bereitgestellte Standardobjektinstanzen (Visual Basic)
Die [My.Forms](../../../visual-basic/language-reference/objects/my-forms-object.md) und [My.WebServices](../../../visual-basic/language-reference/objects/my-webservices-object.md) Objekte bieten Zugriff auf Formulare, Datenquellen und XML-Webdienste, die von der Anwendung verwendet. Dies erfolgt durch Bereitstellen von Sammlungen von *Standardinstanzen* jedes dieser Objekte.  
  
## <a name="default-instances"></a>Standard-Instanzen  
 Eine Standardinstanz ist eine Instanz der Klasse, die von der Laufzeit bereitgestellt wird, und muss nicht werden deklariert und instanziiert wird, mit der `Dim` und `New` Anweisungen. Das folgende Beispiel zeigt, wie Sie möglicherweise haben deklariert und instanziiert eine Instanz von einer <xref:System.Windows.Forms.Form> Klasse mit dem Namen `Form1`, und wie Sie jetzt erhalten Sie eine Standardinstanz dieser <xref:System.Windows.Forms.Form> -Klasse über `My.Forms`.  
  
 [!code-vb[VbVbcnMy#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMy/VB/Class1.vb#5)]  
  
 [!code-vb[VbVbcnMy#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMy/VB/Class1.vb#6)]  
  
 Die `My.Forms` -Objekt gibt eine Auflistung der Standardinstanzen für jede `Form` -Klasse, die in Ihrem Projekt vorhanden ist. Auf ähnliche Weise `My.WebServices` bietet Sie einer Standardinstanz der Proxyklasse für jeden Webdienst, dass Sie einen Verweis auf in Ihrer Anwendung erstellt haben.  
  
## <a name="see-also"></a>Siehe auch

- [My.Forms-Objekt](../../../visual-basic/language-reference/objects/my-forms-object.md)
- [My.WebServices-Objekt](../../../visual-basic/language-reference/objects/my-webservices-object.md)
- [Merkmale von "My" auf Grundlage des Projekttyps](../../../visual-basic/developing-apps/development-with-my/how-my-depends-on-project-type.md)
