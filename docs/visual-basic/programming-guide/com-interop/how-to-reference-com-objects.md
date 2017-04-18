---
title: 'Gewusst wie: Verweisen auf COM-Objekte aus Visual Basic | Microsoft-Dokumentation'
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- COM interop, referencing COM objects
- referencing objects, COM objects from Visual Basic
- objects [Visual Basic], referencing
- COM objects, referencing
- interop assemblies
ms.assetid: 9c518fb4-27d9-4112-9e6a-5a7d0210af6f
caps.latest.revision: 13
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 97c132bcbd36ba7810acadb2aebddc5e84f0b44d
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-reference-com-objects-from-visual-basic"></a>Gewusst wie: Verweisen auf COM-Objekte aus Visual Basic
In [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)], Hinzufügen von Verweisen auf COM-Objekte mit Typbibliotheken erfordert die Erstellung einer Interop-Assembly für die COM-Bibliothek. Verweise auf die Member des COM-Objekts werden an die Interop-Assembly und dann an das eigentliche COM-Objekt weitergeleitet. Antworten vom COM-Objekt werden an die Interop-Assembly und übermittelt die [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] Anwendung.  
  
 Ein COM-Objekt können Sie ohne eine Interop-Assembly die Typinformationen für COM-Objekt in einer .NET Framework-Assembly verweisen. Um Typinformationen einzubetten, legen Sie die `Embed Interop Types` Eigenschaft `True` für den Verweis auf das COM-Objekt. Wenn Sie mit dem Befehlszeilencompiler kompilieren, verwenden Sie die `/link` Option aus, um die COM-Bibliothek zu verweisen. Weitere Informationen finden Sie unter [/Link (Visual Basic)](../../../visual-basic/reference/command-line-compiler/link.md).  
  
 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]Interop-Assemblys erstellt automatisch, wenn Sie einen Verweis auf eine Typbibliothek aus der integrierten Entwicklungsumgebung (IDE) hinzufügen. Wenn Sie über die Befehlszeile arbeiten, können Sie das Tlbimp-Dienstprogramm, Interop-Assemblys manuell zu erstellen.  
  
### <a name="to-add-references-to-com-objects"></a>Hinzufügen von Verweisen auf COM-Objekte  
  
1.  Auf der **Projekt** Menü wählen **Verweis hinzufügen** , und klicken Sie dann auf die **COM** Registerkarte im Dialogfeld.  
  
2.  Wählen Sie die Komponente, die Sie aus der Liste der COM-Objekte verwenden möchten.  
  
3.  Um den Zugriff auf die Interop-Assembly zu vereinfachen, fügen Sie eine `Imports` -Anweisung am Anfang der Klasse oder des Moduls, in dem Sie das COM-Objekt verwenden. Im folgenden Codebeispiel wird importiert z. B. den Namespace `INKEDLib` für Objekte, die in der die `Microsoft InkEdit Control 1.0` Bibliothek.  
  
     [!code-vb[VbVbalrInterop&#40;](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/how-to-reference-com-objects_1.vb)]  
  
### <a name="to-create-an-interop-assembly-using-tlbimp"></a>Erstellen Sie eine Interop-Assembly, die mittels Tlbimp  
  
1.  Fügen Sie den Speicherort von Tlbimp dem Suchpfad hinzu, wenn es nicht bereits Teil des Suchpfads und Sie zurzeit in das Verzeichnis sind, in dem er sich befindet.  
  
2.  Rufen Sie Tlbimp über eine Befehlszeile, die folgenden Informationen angeben:  
  
    -   Name und Speicherort der DLL, die die Typbibliothek enthält.  
  
    -   Name und Speicherort des Namespaces, in dem die Daten platziert werden soll  
  
    -   Name und Speicherort der Ziel-Interop-Assembly  
  
     Der folgende Code veranschaulicht dies:  
  
    ```  
    Tlbimp test3.dll /out:NameSpace1 /out:Interop1.dll  
    ```  
  
     Tlbimp können Sie die um Interop-Assemblys für Typbibliotheken und sogar für nicht registrierte COM-Objekte zu erstellen. Die COM-Objekte, die von Interop-Assemblys bezeichnet müssen jedoch ordnungsgemäß auf dem Computer registriert werden, wo sie sind verwendet werden. Sie können ein COM-Objekt mithilfe der mit dem Betriebssystem Windows enthaltene Dienstprogramm Regsvr32 registrieren.  
  
## <a name="see-also"></a>Siehe auch  
 [COM-Interop](../../../visual-basic/programming-guide/com-interop/index.md)   
 [Tlbimp.exe (Type Library Importer-Tool)](http://msdn.microsoft.com/library/ec0a8d63-11b3-4acd-b398-da1e37e97382)   
 [Tlbexp.exe (Type Library Exporter-Tool)](http://msdn.microsoft.com/library/a487d61b-d166-467b-a7ca-d8b52fbff42d)   
 [Exemplarische Vorgehensweise: Implementieren der Vererbung mit COM-Objekten](../../../visual-basic/programming-guide/com-interop/walkthrough-implementing-inheritance-with-com-objects.md)   
 [Problembehandlung bei der Interoperabilität](../../../visual-basic/programming-guide/com-interop/troubleshooting-interoperability.md)   
 [Imports-Anweisung (.NET-Namespace und -Typ)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)
