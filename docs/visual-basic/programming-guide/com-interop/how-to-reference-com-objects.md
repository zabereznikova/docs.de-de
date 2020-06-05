---
title: 'Gewusst wie: Verweisen auf COM-Objekte aus Visual Basic'
ms.date: 07/20/2015
helpviewer_keywords:
- COM interop [Visual Basic], referencing COM objects
- referencing objects, COM objects from Visual Basic
- objects [Visual Basic], referencing
- COM objects, referencing
- interop assemblies
ms.assetid: 9c518fb4-27d9-4112-9e6a-5a7d0210af6f
ms.openlocfilehash: 2e2cbac6fad5e1686b7383c44619b8c6f5326483
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84396803"
---
# <a name="how-to-reference-com-objects-from-visual-basic"></a>Gewusst wie: Verweisen auf COM-Objekte aus Visual Basic
In Visual Basic erfordert das Hinzufügen von Verweisen auf COM-Objekte, die über Typbibliotheken verfügen, das Erstellen einer Interop-Assembly für die com-Bibliothek. Verweise auf die Member des COM-Objekts werden an die Interop-Assembly weitergeleitet und dann an das tatsächliche com-Objekt weitergeleitet. Antworten aus dem COM-Objekt werden an die Interop-Assembly weitergeleitet und an Ihre .NET Framework Anwendung weitergeleitet.  
  
 Sie können auf ein COM-Objekt verweisen, ohne eine Interopassembly zu verwenden, indem Sie die Typinformationen für das COM-Objekt in eine .NET-Assembly einbetten. Um Typinformationen einzubetten, legen Sie die- `Embed Interop Types` Eigenschaft `True` für den Verweis auf das COM-Objekt auf fest. Wenn Sie mithilfe des Befehlszeilen Compilers kompilieren, verwenden Sie die- `/link` Option, um auf die com-Bibliothek zu verweisen. Weitere Informationen finden Sie unter [Link (Visual Basic)](../../reference/command-line-compiler/link.md).  
  
 Visual Basic erstellt automatisch Interop-Assemblys, wenn Sie einen Verweis auf eine Typbibliothek aus der integrierten Entwicklungsumgebung (Integrated Development Environment, IDE) hinzufügen. Wenn Sie von der Befehlszeile aus arbeiten, können Sie das Hilfsprogramm Tlbimp verwenden, um Interop-Assemblys manuell zu erstellen.  
  
### <a name="to-add-references-to-com-objects"></a>So fügen Sie Verweise auf COM-Objekte hinzu  
  
1. Wählen Sie im Menü **Projekt** die Option **Verweis hinzufügen** aus, und klicken Sie dann im Dialogfeld auf die Registerkarte **com** .  
  
2. Wählen Sie die Komponente aus der Liste der COM-Objekte aus, die Sie verwenden möchten.  
  
3. Fügen Sie zum Vereinfachen des Zugriffs auf die Interop-Assembly am `Imports` Anfang der Klasse oder des Moduls, in dem Sie das COM-Objekt verwenden, eine-Anweisung hinzu. Im folgenden Codebeispiel wird der-Namespace `INKEDLib` für Objekte importiert, auf die in der-Bibliothek verwiesen wird `Microsoft InkEdit Control 1.0` .  
  
     [!code-vb[VbVbalrInterop#40](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#40)]  
  
### <a name="to-create-an-interop-assembly-using-tlbimp"></a>So erstellen Sie eine Interop-Assembly mit Tlbimp  
  
1. Fügen Sie den Speicherort von Tlbimp dem Suchpfad hinzu, wenn er nicht bereits Teil des Suchpfads ist und Sie sich derzeit nicht in dem Verzeichnis befinden, in dem es sich befindet.  
  
2. Wenden Sie Tlbimp über eine Eingabeaufforderung an, und geben Sie dabei die folgenden Informationen an:  
  
    - Name und Speicherort der dll, die die Typbibliothek enthält  
  
    - Name und Speicherort des Namespace, in dem die Informationen abgelegt werden sollen  
  
    - Name und Speicherort der zielinterop-Assembly  
  
     Der folgende Code veranschaulicht dies:  
  
    ```console  
    Tlbimp test3.dll /out:NameSpace1 /out:Interop1.dll  
    ```  
  
     Mit Tlbimp können Sie Interop-Assemblys für Typbibliotheken erstellen, auch für nicht registrierte COM-Objekte. Die COM-Objekte, auf die von Interopassemblys verwiesen wird, müssen jedoch auf dem Computer, auf dem Sie verwendet werden sollen, ordnungsgemäß registriert werden. Sie können ein COM-Objekt registrieren, indem Sie das im Windows-Betriebssystem enthaltene regsvr32-Hilfsprogramm verwenden.  
  
## <a name="see-also"></a>Weitere Informationen

- [COM-Interop](index.md)
- [Tlbimp.exe (Type Library Importer-Tool)](../../../framework/tools/tlbimp-exe-type-library-importer.md)
- [Tlbexp.exe (Type Library Exporter-Tool)](../../../framework/tools/tlbexp-exe-type-library-exporter.md)
- [Exemplarische Vorgehensweise: Implementieren der Vererbung mit COM-Objekten](walkthrough-implementing-inheritance-with-com-objects.md)
- [Problembehandlung bei der Interoperabilität](troubleshooting-interoperability.md)
- [Imports-Anweisung (.NET-Namespace und Typ)](../../language-reference/statements/imports-statement-net-namespace-and-type.md)
