---
title: "Gewusst wie: Hinzufügen von Verweisen zu Typbibliotheken"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- importing type library
- interop assemblies, generating
- type libraries
- COM interop, importing type library
ms.assetid: f5cfa6ba-cc25-4017-82cd-ba7391859113
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e5bbc99c3c40b0864a7c1c25cb79a3d7c26e3a86
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-add-references-to-type-libraries"></a>Gewusst wie: Hinzufügen von Verweisen zu Typbibliotheken
Visual Studio generiert eine Interopassembly mit Metadaten, wenn Sie einer Typbibliothek einen Verweis hinzufügen. Wenn eine primäre Interopassembly verfügbar ist, verwendet Visual Studio die bereits vorhandene Assembly, bevor eine neue Interopassembly generiert wird.  
  
### <a name="to-add-a-reference-to-a-type-library-in-visual-studio"></a>So fügen Sie einer Typbibliothek in Visual Studio einen Verweis hinzu  
  
1.  Installieren Sie die COM DLL- oder EXE-Datei auf Ihrem Computer, es sei denn, die Installation wird mithilfe einer Windows Setup.exe-Datei durchgeführt.  
  
2.  Wählen Sie **Projekt** > **Verweis hinzufügen** aus.  
  
3.  Anschließend wählen Sie im Verweis-Manager **COM** aus.  
  
4.  Wählen Sie die Typbibliothek aus der Liste aus, oder suchen Sie nach der TLB-Datei.  
  
5.  Klicken Sie auf **OK**.  
  
6.  Öffnen Sie im Projektmappen-Explorer das Kontextmenü für den gerade hinzugefügten Verweis, und wählen Sie **Eigenschaften** aus.  
  
7.  Vergewissern Sie sich, dass im Fenster **Eigenschaften** die Eigenschaft **Interop-Typen einbetten** auf **TRUE** festgelegt ist. Daraufhin bettet Visual Studio Typinformationen für COM-Typen in Ihre ausführbaren Dateien ein, sodass keine primären Interopassemblys über Ihre App bereitgestellt werden müssen.  
  
> [!NOTE]
>  Die Menü- und Dialogfeldoptionen können abhängig von der verwendeten Visual Studio-Version variieren.  
  
### <a name="to-add-a-reference-to-a-type-library-for-command-line-compilation"></a>So fügen Sie einer Typbibliothek einen Verweis zur Befehlszeilenkompilierung hinzu  
  
1.  Generieren Sie, wie in [Vorgehensweise: Generieren von Interop-Assemblys aus Typbibliotheken](../../../docs/framework/interop/how-to-generate-interop-assemblies-from-type-libraries.md) beschrieben, eine Interop-Assembly.  
  
2.  Verwenden Sie die Compileroption [/link (C#-Compileroptionen)](~/docs/csharp/language-reference/compiler-options/link-compiler-option.md) oder [/link (Visual Basic)](~/docs/visual-basic/reference/command-line-compiler/link.md) mit dem Namen der Interop-Assembly, um Typinformationen für COM-Typen in Ihre ausführbaren Dateien einzubetten.  
  
## <a name="see-also"></a>Siehe auch  
 [Importing a Type Library as an Assembly (Importieren einer Typbibliothek als Assembly)](../../../docs/framework/interop/importing-a-type-library-as-an-assembly.md)  
 [Verfügbarmachen von COM-Komponenten für .NET Framework](../../../docs/framework/interop/exposing-com-components.md)  
 [Exemplarische Vorgehensweise: Einbetten von Typinformationen aus Microsoft Office-Assemblys](http://msdn.microsoft.com/library/85b55e05-bc5e-4665-b6ae-e1ada9299fd3)  
 [Exemplarische Vorgehensweise: Einbetten von Typen aus verwalteten Assemblys](http://msdn.microsoft.com/library/b28ec92c-1867-4847-95c0-61adfe095e21)  
 [-link (C#-Compileroptionen)](~/docs/csharp/language-reference/compiler-options/link-compiler-option.md)  
 [/link (Visual Basic)](~/docs/visual-basic/reference/command-line-compiler/link.md)
