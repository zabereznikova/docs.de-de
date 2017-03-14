---
title: "How to: Reference COM Objects from Visual Basic | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "COM interop, referencing COM objects"
  - "referencing objects, COM objects from Visual Basic"
  - "objects [Visual Basic], referencing"
  - "COM objects, referencing"
  - "interop assemblies"
ms.assetid: 9c518fb4-27d9-4112-9e6a-5a7d0210af6f
caps.latest.revision: 13
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 13
---
# How to: Reference COM Objects from Visual Basic
[!INCLUDE[vs2017banner](~/includes/vs2017banner.md)]

In [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] müssen Sie zum Hinzufügen von Verweisen auf COM\-Objekte mit Typbibliotheken eine Interopassembly für die COM\-Bibliothek erstellen.  Verweise auf Member des COM\-Objekts werden an die Interop\-Assembly und dann an das eigentliche COM\-Objekt weitergeleitet.  Antworten vom COM\-Objekt werden an die Interopassembly und von dort an Ihre [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]\-Anwendung weitergeleitet.  
  
 Sie können auf ein COM\-Objekt verweisen, ohne eine Interopassembly zu erstellen, indem Sie die Typinformationen für das COM\-Objekt in eine .NET\-Assembly einbetten.  Zum Einbetten der Typinformationen legen Sie die `Embed Interop Types`\-Eigenschaft für den Verweis auf das COM\-Objekt auf `True` fest.  Wenn Sie mit dem Befehlszeilencompiler kompilieren, verwenden Sie die `/link`\-Option, um auf die COM\-Bibliothek zu verweisen.  Weitere Informationen finden Sie unter [\/link](../../../visual-basic/reference/command-line-compiler/link.md).  
  
 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] erstellt automatisch Interopassemblys, wenn Sie einen Verweis auf eine Typbibliothek der integrierten Entwicklungsumgebung \(IDE\) hinzufügen.  Über die Befehlszeile können Sie mit dem Dienstprogramm Tlbimp manuell Interop\-Assemblys erstellen.  
  
### So fügen Sie Verweise auf COM\-Objekte hinzu  
  
1.  Klicken Sie im Menü **Projekt** auf **Verweis hinzufügen**, und klicken Sie anschließend im Dialogfeld auf die Registerkarte **COM**.  
  
2.  Wählen Sie in der Liste der COM\-Objekte die zu verwendende Komponente aus.  
  
3.  Um den Zugriff auf die Interop\-Assembly zu vereinfachen, fügen Sie am Anfang der Klasse oder des Moduls, in der bzw. dem Sie das COM\-Objekt verwenden, eine `Imports`\-Anweisung ein.  Im folgenden Codebeispiel wird z. B. der Namespace `INKEDLib` für Objekte importiert, auf die in der Bibliothek `Microsoft InkEdit Control 1.0` verwiesen wird.  
  
     [!code-vb[VbVbalrInterop#40](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/how-to-reference-com-objects_1.vb)]  
  
### So erstellen Sie mit Tlbimp eine Interop\-Assembly  
  
1.  Fügen Sie den Speicherort von Tlbimp dem Suchpfad hinzu, sofern der Speicherort nicht bereits darin enthalten ist und Sie nicht gerade in diesem Verzeichnis arbeiten.  
  
2.  Rufen Sie Tlbimp über die Eingabeaufforderung auf, und geben Sie folgende Informationen an:  
  
    -   Name und Speicherort der DLL, die die Typbibliothek enthält  
  
    -   Name und Speicherort des Namespaces, in dem die Informationen abgelegt werden sollen  
  
    -   Name und Speicherort der Ziel\-Interop\-Assembly  
  
     Der folgende Code veranschaulicht dies:  
  
    ```  
    Tlbimp test3.dll /out:NameSpace1 /out:Interop1.dll  
    ```  
  
     Sie können mit Tlbimp Interop\-Assemblys für Typbibliotheken und sogar für nicht registrierte COM\-Objekte erstellen.  Die COM\-Objekte, auf die über Interop\-Assemblys verwiesen wird, müssen jedoch auf dem Computer, auf dem sie verwendet werden, ordnungsgemäß registriert sein.  Sie können ein COM\-Objekt mit dem in Windows enthaltenen Dienstprogramm Regsvr32 registrieren.  
  
## Siehe auch  
 [COM Interop](../../../visual-basic/programming-guide/com-interop/index.md)   
 [Tlbimp.exe \(Type Library Importer\)](../Topic/Tlbimp.exe%20\(Type%20Library%20Importer\).md)   
 [Tlbexp.exe \(Type Library Exporter\)](../Topic/Tlbexp.exe%20\(Type%20Library%20Exporter\).md)   
 [Walkthrough: Implementing Inheritance with COM Objects](../../../visual-basic/programming-guide/com-interop/walkthrough-implementing-inheritance-with-com-objects.md)   
 [Troubleshooting Interoperability](../../../visual-basic/programming-guide/com-interop/troubleshooting-interoperability.md)   
 [Imports Statement \(.NET Namespace and Type\)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)