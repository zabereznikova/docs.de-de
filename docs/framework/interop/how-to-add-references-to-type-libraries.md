---
title: 'Vorgehensweise: Hinzufügen von Verweisen zu Typbibliotheken'
ms.date: 03/30/2017
helpviewer_keywords:
- importing type library
- interop assemblies, generating
- type libraries
- COM interop, importing type library
ms.assetid: f5cfa6ba-cc25-4017-82cd-ba7391859113
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4f0f254b7794ce1cd4c765bee70c78e3c60a14aa
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69946493"
---
# <a name="how-to-add-references-to-type-libraries"></a>Vorgehensweise: Hinzufügen von Verweisen zu Typbibliotheken
Visual Studio generiert eine Interopassembly mit Metadaten, wenn Sie einer Typbibliothek einen Verweis hinzufügen. Wenn eine primäre Interopassembly verfügbar ist, verwendet Visual Studio die bereits vorhandene Assembly, bevor eine neue Interopassembly generiert wird.  
  
### <a name="to-add-a-reference-to-a-type-library-in-visual-studio"></a>So fügen Sie einer Typbibliothek in Visual Studio einen Verweis hinzu  
  
1. Installieren Sie die COM DLL- oder EXE-Datei auf Ihrem Computer, es sei denn, die Installation wird mithilfe einer Windows Setup.exe-Datei durchgeführt.  
  
2. Wählen Sie **Projekt** > **Verweis hinzufügen** aus.  
  
3. Anschließend wählen Sie im Verweis-Manager **COM** aus.  
  
4. Wählen Sie die Typbibliothek aus der Liste aus, oder suchen Sie nach der TLB-Datei.  
  
5. Klicken Sie auf **OK**.  
  
6. Öffnen Sie im Projektmappen-Explorer das Kontextmenü für den gerade hinzugefügten Verweis, und wählen Sie **Eigenschaften** aus.  
  
7. Vergewissern Sie sich, dass im Fenster **Eigenschaften** die Eigenschaft **Interop-Typen einbetten** auf **TRUE** festgelegt ist. Daraufhin bettet Visual Studio Typinformationen für COM-Typen in Ihre ausführbaren Dateien ein, sodass keine primären Interopassemblys über Ihre App bereitgestellt werden müssen.  
  
> [!NOTE]
> Die Menü- und Dialogfeldoptionen können abhängig von der verwendeten Visual Studio-Version variieren.  
  
### <a name="to-add-a-reference-to-a-type-library-for-command-line-compilation"></a>So fügen Sie einer Typbibliothek einen Verweis zur Befehlszeilenkompilierung hinzu  
  
1. Generieren Sie eine Interopassembly wie unter [Vorgehensweise: Generieren von Interopassemblys aus Typbibliotheken](how-to-generate-interop-assemblies-from-type-libraries.md) beschrieben.  
  
2. Verwenden Sie die Compileroption [/link (C#-Compileroptionen)](../../csharp/language-reference/compiler-options/link-compiler-option.md) oder [/link (Visual Basic)](../../visual-basic/reference/command-line-compiler/link.md) mit dem Namen der Interop-Assembly, um Typinformationen für COM-Typen in Ihre ausführbaren Dateien einzubetten.  
  
## <a name="see-also"></a>Siehe auch

- [Importing a Type Library as an Assembly (Importieren einer Typbibliothek als Assembly)](importing-a-type-library-as-an-assembly.md)
- [Verfügbarmachen von COM-Komponenten für .NET Framework](exposing-com-components.md)
- [Exemplarische Vorgehensweise: Einbetten von Typen aus verwalteten Assemblys in Visual Studio (C#)](../../csharp/programming-guide/concepts/assemblies-gac/walkthrough-embedding-types-from-managed-assemblies-in-visual-studio.md) 
- [Exemplarische Vorgehensweise: Embedding Types from Managed Assemblies in Visual Studio (Visual Basic)](../../visual-basic/programming-guide/concepts/assemblies-gac/walkthrough-embedding-types-from-managed-assemblies-in-vs.md) (Exemplarische Vorgehensweise: Einbetten von Typen aus verwalteten Assemblys in Visual Studio (Visual Basic))
- [-link (C#-Compileroptionen)](../../csharp/language-reference/compiler-options/link-compiler-option.md)
- [/link (Visual Basic)](../../visual-basic/reference/command-line-compiler/link.md)
