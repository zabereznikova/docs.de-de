---
title: "How to: Add References to Type Libraries | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "importing type library"
  - "interop assemblies, generating"
  - "type libraries"
  - "COM interop, importing type library"
ms.assetid: f5cfa6ba-cc25-4017-82cd-ba7391859113
caps.latest.revision: 12
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 12
---
# How to: Add References to Type Libraries
Visual Studio generiert eine Interopassembly mit Metadaten, wenn Sie einer Typbibliothek einen Verweis hinzufügen.  Wenn eine primäre Interopassembly verfügbar ist, verwendet Visual Studio die bereits vorhandene Assembly, bevor eine neue Interopassembly generiert wird.  
  
### So fügen Sie einer Typbibliothek in Visual Studio einen Verweis hinzu  
  
1.  Installieren Sie die COM DLL\- oder EXE\-Datei auf Ihrem Computer, es sei denn, die Installation wird mithilfe einer Windows Setup.exe\-Datei durchgeführt.  
  
2.  Wählen Sie **Projekt**, **Verweis hinzufügen** aus.  
  
3.  Anschließend wählen Sie im Verweis\-Manager **COM** aus.  
  
4.  Wählen Sie die Typbibliothek aus der Liste aus, oder suchen Sie nach der TLB\-Datei.  
  
5.  Klicken Sie auf **OK**.  
  
6.  Öffnen Sie im Projektmappen\-Explorer das Kontextmenü für den gerade hinzugefügten Verweis, und wählen Sie **Eigenschaften** aus.  
  
7.  Vergewissern Sie sich, dass im Fenster **Eigenschaften** die Eigenschaft **Interoptypen einbetten** auf **True** festgelegt ist.  Daraufhin bettet Visual Studio Typinformationen für COM\-Typen in Ihre ausführbaren Dateien ein, sodass keine primären Interopassemblys über Ihre App bereitgestellt werden müssen.  
  
> [!NOTE]
>  Die Menü\- und Dialogfeldoptionen können abhängig von der verwendeten Visual Studio\-Version variieren.  
  
### So fügen Sie einer Typbibliothek einen Verweis zur Befehlszeilenkompilierung hinzu  
  
1.  Generieren Sie eine Interopassembly wie in [How to: Generate Interop Assemblies from Type Libraries](../../../docs/framework/interop/how-to-generate-interop-assemblies-from-type-libraries.md) beschrieben.  
  
2.  Verwenden Sie die [\/link \(Link to COM Assembly\)](../Topic/-link%20\(C%23%20Compiler%20Options\).md)\- oder [\/link](../Topic/-link%20\(Visual%20Basic\).md)\-Compileroption mit dem Namen der Interopassembly, um Typinformationen für COM\-Typen in Ihre ausführbaren Dateien einzubetten.  
  
## Siehe auch  
 [Importing a Type Library as an Assembly](../../../docs/framework/interop/importing-a-type-library-as-an-assembly.md)   
 [Exposing COM Components to the .NET Framework](../../../docs/framework/interop/exposing-com-components.md)   
 [Exemplarische Vorgehensweise: Einbetten von Typinformationen aus Microsoft Office\-Assemblys](../Topic/Walkthrough:%20Embedding%20Type%20Information%20from%20Microsoft%20Office%20Assemblies%20\(C%23%20and%20Visual%20Basic\).md)   
 [Exemplarische Vorgehensweise: Einbetten von Typen aus verwalteten Assemblys](../Topic/Walkthrough:%20Embedding%20Types%20from%20Managed%20Assemblies%20\(C%23%20and%20Visual%20Basic\).md)   
 [\/link \(Link to COM Assembly\)](../Topic/-link%20\(C%23%20Compiler%20Options\).md)   
 [\/link](../Topic/-link%20\(Visual%20Basic\).md)