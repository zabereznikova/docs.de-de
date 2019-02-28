---
title: 'Vorgehensweise: COM-Verweisobjekte aus Visual Basic'
ms.date: 07/20/2015
helpviewer_keywords:
- COM interop [Visual Basic], referencing COM objects
- referencing objects, COM objects from Visual Basic
- objects [Visual Basic], referencing
- COM objects, referencing
- interop assemblies
ms.assetid: 9c518fb4-27d9-4112-9e6a-5a7d0210af6f
ms.openlocfilehash: 9e88f5f093ce55d3d80da9b38689016872ea12cb
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2019
ms.locfileid: "56980190"
---
# <a name="how-to-reference-com-objects-from-visual-basic"></a>Vorgehensweise: COM-Verweisobjekte aus Visual Basic
In Visual Basic ist beim Hinzufügen von Verweisen auf COM-Objekte, die über Typbibliotheken verfügen die Erstellung einer Interop-Assembly für COM-Bibliothek erforderlich. Verweise auf die Member des COM-Objekts sind die interop-Assembly an, und klicken Sie dann auf die tatsächliche COM-Objekt weitergeleitet. Antworten von der COM-Objekt an die Interop-Assembly und weitergeleitet wird, um Ihre [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] Anwendung.  
  
 Sie können ein COM-Objekt verweisen, ohne eine interop-Assembly die Typinformationen für COM-Objekts in einer .NET-Assembly. Legen Sie zum Einbetten von Typinformationen der `Embed Interop Types` Eigenschaft `True` für den Verweis auf das COM-Objekt. Wenn Sie mithilfe des Befehlszeilencompilers kompilieren, verwenden Sie die `/link` Option aus, um die COM-Bibliothek verweisen. Weitere Informationen finden Sie unter [/Link (Visual Basic)](../../../visual-basic/reference/command-line-compiler/link.md).  
  
 Visual Basic erstellt automatisch interop-Assemblys auf, wenn Sie einen Verweis auf eine Typbibliothek aus der integrierten Entwicklungsumgebung (IDE) hinzufügen. Wenn Sie über die Befehlszeile arbeiten, können Sie das Tlbimp-Dienstprogramm, interop-Assemblys manuell zu erstellen.  
  
### <a name="to-add-references-to-com-objects"></a>Zum Hinzufügen von Verweisen auf COM-Objekte  
  
1.  Auf der **Projekt** Menü wählen **Verweis hinzufügen** , und klicken Sie dann auf die **COM** Registerkarte im Dialogfeld.  
  
2.  Wählen Sie die Komponente, die Sie aus der Liste der COM-Objekte verwenden möchten.  
  
3.  Um den Zugriff auf die interop-Assembly zu vereinfachen, fügen eine `Imports` Anweisung am Anfang der Klasse oder das Modul, in dem Sie das COM-Objekt verwenden. Das folgende Codebeispiel importiert z. B. den Namespace `INKEDLib` für Objekte, die auf die verwiesen wird der `Microsoft InkEdit Control 1.0` Bibliothek.  
  
     [!code-vb[VbVbalrInterop#40](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#40)]  
  
### <a name="to-create-an-interop-assembly-using-tlbimp"></a>Eine Interop-Assembly, die über "Tlbimp" erstellen  
  
1.  Fügen Sie den Speicherort des "Tlbimp" dem Suchpfad hinzu, wenn es nicht bereits Teil des Pfads für die Suche und Sie aktuell nicht in das Verzeichnis werden, in dem er sich befindet.  
  
2.  Rufen Sie "Tlbimp" über eine Eingabeaufforderung, die die folgenden Informationen angeben:  
  
    -   Name und Speicherort der DLL, die die Typbibliothek enthält.  
  
    -   Name und Speicherort des Namespace, in dem die Informationen platziert werden soll  
  
    -   Name und Speicherort der Ziel-Interop-Assembly  
  
     Der folgende Code veranschaulicht dies:  
  
    ```  
    Tlbimp test3.dll /out:NameSpace1 /out:Interop1.dll  
    ```  
  
     Sie können "Tlbimp" verwenden, um interop-Assemblys für Typbibliotheken und sogar für nicht registrierte COM-Objekte zu erstellen. Die COM-Objekte, die interop-Assemblys verweist müssen jedoch ordnungsgemäß auf dem Computer registriert werden, wo sie sind, verwendet werden soll. Sie können ein COM-Objekt registrieren, mit dem Dienstprogramm "Regsvr32" mit dem Windows-Betriebssystem enthalten.  
  
## <a name="see-also"></a>Siehe auch

- [COM-Interop](../../../visual-basic/programming-guide/com-interop/index.md)
- [Tlbimp.exe (Type Library Importer-Tool)](../../../framework/tools/tlbimp-exe-type-library-importer.md)
- [Tlbexp.exe (Type Library Exporter-Tool)](../../../framework/tools/tlbexp-exe-type-library-exporter.md)
- [Exemplarische Vorgehensweise: Implementieren der Vererbung mit COM-Objekten](../../../visual-basic/programming-guide/com-interop/walkthrough-implementing-inheritance-with-com-objects.md)
- [Problembehandlung bei der Interoperabilität](../../../visual-basic/programming-guide/com-interop/troubleshooting-interoperability.md)
- [Imports-Anweisung (.NET-Namespace und -Typ)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)
