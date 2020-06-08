---
title: Von My.Forms und My.WebServices bereitgestellte Standardobjektinstanzen
ms.date: 07/20/2015
helpviewer_keywords:
- My.WebServices object [Visual Basic], developing applications
- My.Forms object [Visual Basic], developing applications
- rapid application development (RAD), My.Forms
- rapid application development (RAD), My.WebServices
ms.assetid: de930027-9108-4f0c-b97c-5e7db4d6ef79
ms.openlocfilehash: 847724450ee2bc8bc591371f71171e8ba4ed9337
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84411739"
---
# <a name="default-object-instances-provided-by-myforms-and-mywebservices-visual-basic"></a>Von My.Forms und My.WebServices bereitgestellte Standardobjektinstanzen (Visual Basic)

Die Objekte [My.Forms](../../language-reference/objects/my-forms-object.md) und [My.WebServices](../../language-reference/objects/my-webservices-object.md), ermöglichen den Zugriff auf Formulare, Datenquellen und XML-Webdienste, die von der Anwendung verwendet werden. Hierfür werden Sammlungen mit den *Standardinstanzen* jedes dieser Objekte bereitgestellt.  
  
## <a name="default-instances"></a>Standardinstanzen  

 Eine Standardinstanz ist eine Instanz der Klasse, die von der Runtime bereitgestellt wird und nicht mit den Anweisungen `Dim` und `New` deklariert und instanziiert werden muss. Im folgenden Beispiel wird veranschaulicht, wie Sie mit einer deklarierten und instanziierten Instanz einer <xref:System.Windows.Forms.Form>-Klasse namens `Form1` eine Standardinstanz dieser <xref:System.Windows.Forms.Form>-Klasse über `My.Forms` erstellen können.  
  
 [!code-vb[VbVbcnMy#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMy/VB/Class1.vb#5)]  
  
 [!code-vb[VbVbcnMy#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMy/VB/Class1.vb#6)]  
  
 Das `My.Forms`-Objekt gibt eine Sammlung der Standardinstanzen für jede `Form`-Klasse zurück, die in Ihrem Projekt vorhanden ist. Ebenso stellt `My.WebServices` eine Standardinstanz der Proxyklasse für jeden Webdienst bereit, auf den Sie in der Anwendung einen Verweis erstellt haben.  
  
## <a name="see-also"></a>Siehe auch

- [My.Forms-Objekt](../../language-reference/objects/my-forms-object.md)
- [My.WebServices-Objekt](../../language-reference/objects/my-webservices-object.md)
- [Merkmale von "My" auf Grundlage des Projekttyps](how-my-depends-on-project-type.md)
