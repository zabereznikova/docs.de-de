---
title: Erstellen von Office Open XML-Quelldokument (Visual Basic) | Microsoft-Dokumentation
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 61ccd6fb-0c47-4075-afdf-5b5021330f21
caps.latest.revision: 3
author: stevehoag
ms.author: shoag
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 928a3c34836464e7603c485b64c9c426913ae7b2
ms.lasthandoff: 03/13/2017


---
# <a name="creating-the-source-office-open-xml-document-visual-basic"></a>Erstellen von Office Open XML-Quelldokument (Visual Basic)
In diesem Thema wird das Erstellen des Office Open XML-WordprocessingML-Dokuments erläutert, das in den anderen Beispielen in diesem Lernprogramm verwendet wird. Wenn Sie diese Anweisungen befolgen, entspricht Ihre Ausgabe der Ausgabe im jeweiligen Beispiel.  
  
 Die Beispiele in diesem Lernprogramm funktionieren mit jedem gültigen WordprocessingML-Dokument.  
  
 Erstellen Sie das Dokument, um dieses Lernprogramm verwendet, Sie müssen entweder Microsoft Office 2007 oder höher installiert haben oder benötigen Sie Microsoft Office 2003 mit Microsoft Office Compatibility Pack für Word, Excel und PowerPoint 2007-Dateiformate.  
  
## <a name="creating-the-wordprocessingml-document"></a>Erstellen des WordprocessingML-Dokuments  
  
#### <a name="to-create-the-wordprocessingml-document"></a>So erstellen Sie das WordprocessingML-Dokument  
  
1.  Erstellen Sie ein neues Microsoft Word-Dokument.  
  
2.  Fügen Sie in das neue Dokument den folgenden Text ein:  
  
    ```  
    Parsing WordprocessingML with LINQ to XML  
  
    The following example prints to the console.  
  
    Imports System  
  
    Class Program  
        Public Shared  Sub Main(ByVal args() As String)  
            Console.WriteLine("Hello World")  
        End Sub  
    End Class  
  
    This example produces the following output:  
  
    Hello World  
    ```  
  
3.  Formatieren Sie die erste Zeile mit der Formatvorlage "Überschrift 1".  
  
4.  Wählen Sie die Zeilen, die Visual Basic-Code enthalten. Die erste Zeile beginnt mit dem `Imports`-Schlüsselwort. Die letzte Zeile ist "End Class". Formatieren Sie die Zeilen mit der Schriftart Courier. Formatieren Sie sie anschließend mit einer neuen Formatvorlage, und geben Sie der neuen Formatvorlage den Namen "Code".  
  
5.  Wählen Sie zum Schluss die gesamte Zeile aus, die die Ausgabe enthält, und formatieren Sie sie mit der `Code`-Formatvorlage.  
  
6.  Speichern Sie das Dokument, und nennen Sie es <legacyBold>SampleDoc.docx</legacyBold>.  
  
    > [!NOTE]
    >  Wenn Sie Microsoft Word 2003 verwenden, wählen Sie **Word 2007-Dokument** in der **Dateityp** Dropdown-Liste.  
  
## <a name="see-also"></a>Siehe auch  
 [Lernprogramm: Bearbeiten von Inhalten in einem WordprocessingML-Dokument (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/tutorial-manipulating-content-in-a-wordprocessingml-document.md)
