---
title: Von My.Forms und My.WebServices bereitgestellte Standardobjektinstanzen
ms.date: 07/20/2015
helpviewer_keywords:
- My.WebServices object [Visual Basic], developing applications
- My.Forms object [Visual Basic], developing applications
- rapid application development (RAD), My.Forms
- rapid application development (RAD), My.WebServices
ms.assetid: de930027-9108-4f0c-b97c-5e7db4d6ef79
ms.openlocfilehash: d06df4bd023892429b2aaefdd624398a6546d06d
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74330203"
---
# <a name="default-object-instances-provided-by-myforms-and-mywebservices-visual-basic"></a>Von My.Forms und My.WebServices bereitgestellte Standardobjektinstanzen (Visual Basic)

Die Objekte [My. Forms](../../../visual-basic/language-reference/objects/my-forms-object.md) und [My. Webservices](../../../visual-basic/language-reference/objects/my-webservices-object.md) ermöglichen den Zugriff auf Formulare, Datenquellen und XML-Webdienste, die von Ihrer Anwendung verwendet werden. Hierzu werden Auflistungen von *Standard Instanzen* der einzelnen Objekte bereitgestellt.  
  
## <a name="default-instances"></a>Standard Instanzen  

 Eine Standard Instanz ist eine Instanz der-Klasse, die von der Laufzeit bereitgestellt wird und nicht mit den Anweisungen `Dim` und `New` deklariert und instanziiert werden muss. Im folgenden Beispiel wird veranschaulicht, wie Sie eine Instanz einer <xref:System.Windows.Forms.Form>-Klasse mit dem Namen `Form1`deklarieren und instanziiert haben und wie Sie jetzt eine Standard Instanz dieser <xref:System.Windows.Forms.Form> Klasse über `My.Forms`erhalten können.  
  
 [!code-vb[VbVbcnMy#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMy/VB/Class1.vb#5)]  
  
 [!code-vb[VbVbcnMy#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMy/VB/Class1.vb#6)]  
  
 Das `My.Forms`-Objekt gibt eine Auflistung von Standard Instanzen für jede `Form`-Klasse zurück, die in Ihrem Projekt vorhanden ist. Ebenso stellt `My.WebServices` eine Standard Instanz der Proxy Klasse für jeden Webdienst bereit, auf den Sie in der Anwendung einen Verweis erstellt haben.  
  
## <a name="see-also"></a>Siehe auch

- [My.Forms-Objekt](../../../visual-basic/language-reference/objects/my-forms-object.md)
- [My.WebServices-Objekt](../../../visual-basic/language-reference/objects/my-webservices-object.md)
- [Merkmale von "My" auf Grundlage des Projekttyps](../../../visual-basic/developing-apps/development-with-my/how-my-depends-on-project-type.md)
