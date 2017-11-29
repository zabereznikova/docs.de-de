---
title: 'Gewusst wie: Verweisen auf COM-Objekte aus Visual Basic'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- COM interop [Visual Basic], referencing COM objects
- referencing objects, COM objects from Visual Basic
- objects [Visual Basic], referencing
- COM objects, referencing
- interop assemblies
ms.assetid: 9c518fb4-27d9-4112-9e6a-5a7d0210af6f
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 694bd74e2b5ae374269accd845fe9178958bf56c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-reference-com-objects-from-visual-basic"></a>Gewusst wie: Verweisen auf COM-Objekte aus Visual Basic
In [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)], Hinzufügen von Verweisen auf COM-Objekte, die Typbibliotheken verfügen, ist die Erstellung einer Interop-Assembly für COM-Bibliothek erforderlich. Verweise auf die Member des COM-Objekts sind auf die Interop-Assembly weitergeleitet, und klicken Sie dann auf das eigentliche COM-Objekt weitergeleitet. Antworten von der COM-Objekt an die Interop-Assembly weitergeleitet und an weitergeleitet werden Ihre [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] Anwendung.  
  
 Sie können ein COM-Objekt verweisen, ohne die Typinformationen für COM-Objekts in eine .NET-Assembly mithilfe einer Interop-Assembly. Um Typinformationen einzubetten, legen die `Embed Interop Types` Eigenschaft `True` für den Verweis auf das COM-Objekt. Wenn Sie mithilfe des Befehlszeilencompilers kompilieren, verwenden Sie die `/link` Option aus, um die COM-Bibliothek verweisen. Weitere Informationen finden Sie unter [/Link (Visual Basic)](../../../visual-basic/reference/command-line-compiler/link.md).  
  
 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]Interop-Assemblys erstellt automatisch, wenn Sie einen Verweis auf eine Typbibliothek aus der integrierten Entwicklungsumgebung (IDE) hinzufügen. Wenn Sie über die Befehlszeile zu arbeiten, können Sie das Tlbimp-Dienstprogramm, Interop-Assemblys manuell zu erstellen.  
  
### <a name="to-add-references-to-com-objects"></a>Hinzufügen von Verweisen auf COM-Objekte  
  
1.  Auf der **Projekt** Menü wählen **Verweis hinzufügen** , und klicken Sie dann auf die **COM** Registerkarte im Dialogfeld.  
  
2.  Wählen Sie die Komponente, die Sie aus der Liste der COM-Objekte verwenden möchten.  
  
3.  Um den Zugriff auf die Interop-Assembly zu vereinfachen, fügen Sie eine `Imports` Anweisungen am Anfang der Klasse oder des Moduls, in dem Sie das COM-Objekt verwenden. Im folgenden Codebeispiel wird importiert z. B. den Namespace `INKEDLib` für Objekte der `Microsoft InkEdit Control 1.0` Bibliothek.  
  
     [!code-vb[VbVbalrInterop#40](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/how-to-reference-com-objects_1.vb)]  
  
### <a name="to-create-an-interop-assembly-using-tlbimp"></a>Zum Erstellen einer Interop-Assembly, die mithilfe von Tlbimp  
  
1.  Fügen Sie den Speicherort der Tlbimp den Suchpfad hinzu, wenn er nicht bereits Teil des Suchpfades und Sie nicht im Verzeichnis momentan, in dem er sich befindet.  
  
2.  Rufen Sie Tlbimp aus der Eingabeaufforderung die folgenden Informationen angeben:  
  
    -   Name und Speicherort der DLL, die die Typbibliothek enthält.  
  
    -   Name und Speicherort des Namespace, in dem die Informationen platziert werden soll  
  
    -   Name und Speicherort der Ziel-Interop-Assembly  
  
     Der folgende Code veranschaulicht dies:  
  
    ```  
    Tlbimp test3.dll /out:NameSpace1 /out:Interop1.dll  
    ```  
  
     Sie können Tlbimp verwenden, Erstellen von Interop-Assemblys für Typbibliotheken und sogar für nicht registrierte COM-Objekte. Die COM-Objekte verweist Interop-Assemblys müssen jedoch ordnungsgemäß auf dem Computer registriert werden, in denen sie verwendet werden, werden. Sie können ein COM-Objekt registrieren, mit dem Dienstprogramm "regsvr32" mit dem Windows-Betriebssystem enthalten.  
  
## <a name="see-also"></a>Siehe auch  
 [COM-Interop](../../../visual-basic/programming-guide/com-interop/index.md)  
 [Tlbimp.exe (Type Library Importer-Tool)](http://msdn.microsoft.com/library/ec0a8d63-11b3-4acd-b398-da1e37e97382)  
 [Tlbexp.exe (Type Library Exporter-Tool)](http://msdn.microsoft.com/library/a487d61b-d166-467b-a7ca-d8b52fbff42d)  
 [Exemplarische Vorgehensweise: Implementieren der Vererbung mit COM-Objekten](../../../visual-basic/programming-guide/com-interop/walkthrough-implementing-inheritance-with-com-objects.md)  
 [Problembehandlung bei der Interoperabilität](../../../visual-basic/programming-guide/com-interop/troubleshooting-interoperability.md)  
 [Imports-Anweisung (.NET-Namespace und -Typ)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)
