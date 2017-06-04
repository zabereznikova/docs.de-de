---
title: "Exposing COM Components to the .NET Framework | Microsoft Docs"
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
  - "exposing COM components to .NET Framework"
  - "interoperation with unmanaged code, exposing COM components"
  - "COM interop, exposing COM components"
ms.assetid: e78b14f1-e487-43cd-9c6d-1a07483f1730
caps.latest.revision: 11
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 11
---
# Exposing COM Components to the .NET Framework
In diesem Abschnitt wird der Prozess zusammengefasst, der zum Verfügbarmachen vorhandener COM\-Komponenten in verwaltetem Code erforderlich ist.  Detaillierte Informationen zum Schreiben von COM\-Servern, die eng in .NET Framework eingebunden sind, finden Sie unter [Entwurfsüberlegungen für die Interoperation](http://msdn.microsoft.com/de-de/b59637f6-fe35-40d6-ae72-901e7a707689).  
  
 Vorhandene COM\-Komponenten können in verwaltetem Code als Geschäftsanwendungen mittlerer Ebene oder als isolierte Funktionen verwendet werden.  Idealerweise verfügt eine Komponente über eine primäre Interop\-Assembly und entspricht weitestgehend den Programmierstandards von COM.  
  
#### So machen Sie COM\-Komponenten in .NET Framework verfügbar  
  
1.  [Importieren Sie eine Typbibliothek als Assembly](../../../docs/framework/interop/importing-a-type-library-as-an-assembly.md).  
  
     Common Language Runtime benötigt Metadaten für alle Typen, einschließlich COM\-Typen.  Es gibt verschiedene Möglichkeiten, um eine Assembly zu erhalten, die als Metadaten importierte COM\-Typen enthält.  
  
2.  [Erstellen Sie COM\-Typen in verwaltetem Code](http://msdn.microsoft.com/de-de/1a95a8ca-c8b8-4464-90b0-5ee1a1135b66).  
  
     Für das COM\-Objekt können Sie in gleicher Weise COM\-Typen überprüfen, Instanzen aktivieren und Methoden aufrufen wie für einen verwalteten Typ.  
  
3.  [Kompilieren Sie ein Interop\-Projekt](../../../docs/framework/interop/compiling-an-interop-project.md).  
  
     Mit [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)] stehen für Compiler mehrere mit der CLS \(Common Language Specification\) kompatible Programmiersprachen zur Verfügung, z. B. [!INCLUDE[vbprvblong](../../../includes/vbprvblong-md.md)], C\# und C\+\+.  
  
4.  [Geben Sie eine Interop\-Anwendung weiter](../../../docs/framework/interop/deploying-an-interop-application.md).  
  
     Interop\-Anwendungen werden am besten als signierte Assemblys mit [starkem Namen](../../../docs/framework/app-domains/strong-named-assemblies.md) im globalen Assemblycache bereitgestellt.  
  
## Siehe auch  
 [Interoperating with Unmanaged Code](../../../docs/framework/interop/index.md)   
 [Design Considerations for Interoperation](http://msdn.microsoft.com/de-de/b59637f6-fe35-40d6-ae72-901e7a707689)   
 [COM Interop Sample: .NET Client and COM Server](../../../docs/framework/interop/com-interop-sample-net-client-and-com-server.md)   
 [Sprachenunabhängigkeit und sprachunabhängige Komponenten](../../../docs/standard/language-independence-and-language-independent-components.md)   
 [Gacutil.exe \(Global Assembly Cache Tool\)](../../../docs/framework/tools/gacutil-exe-gac-tool.md)