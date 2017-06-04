---
title: "Gewusst wie: Suchen von Assemblys mit DEVPATH | Microsoft Docs"
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
  - ".NET Framework-Anwendungskonfiguration, Assemblys"
  - "app.config-Dateien, Assemblyspeicherorte"
  - "Anwendungskonfigurationsdateien, Festlegen des Speicherorts einer Assembly"
  - "Assemblys [.NET Framework], Speicherort"
  - "DEVPATH"
  - "Suchen von Assemblys"
ms.assetid: 44d2eadf-7eec-443c-a2ac-d601fd919e17
caps.latest.revision: 8
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 8
---
# Gewusst wie: Suchen von Assemblys mit DEVPATH
Unter Umständen möchten Entwickler sicherstellen, dass eine freigegebene Assembly mit mehreren Anwendungen korrekt zusammenarbeitet.  Um die Assembly während des Entwicklungszyklus nicht jedes Mal in den globalen Assemblycache laden zu müssen, kann eine **DEVPATH**\-Umgebungsvariable erstellt werden, die auf das Buildausgabeverzeichnis zeigt.  
  
 Angenommen, Sie erstellen eine freigegebene Assembly mit dem Namen **MySharedAssembly**, und das Ausgabeverzeichnis lautet **C:\\MySharedAssembly\\Debug**.  Sie können **C:\\MySharedAssembly\\Debug** in die **DEVPATH**\-Variable einbinden.  Sie müssen [\<developmentMode\>](../../../docs/framework/configure-apps/file-schema/runtime/developmentmode-element.md) dem Element in der Computerkonfigurationsdatei festlegen.  Dieses Element weist die Common Language Runtime an, bei der Suche nach Assemblys auf **DEVPATH** zurückzugreifen.  
  
 Die freigegebene Assembly muss von der Laufzeit erkannt werden.  Um ein privates Verzeichnis zum Auflösen von Assemblyverweisen festzulegen, verwenden Sie [\<codeBase\>\-Element](../../../docs/framework/configure-apps/file-schema/runtime/codebase-element.md) oder [\<probing\>\-Element](../../../docs/framework/configure-apps/file-schema/runtime/probing-element.md) in einer Konfigurationsdatei, wie in [Festlegen des Speicherortes einer Assembly](../../../docs/framework/configure-apps/specify-assembly-location.md) beschrieben.  Sie können die Assembly auch in einem Unterverzeichnis des Anwendungsverzeichnisses ablegen.  Weitere Informationen finden Sie unter [So sucht Common Language Runtime nach Assemblys](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md).  
  
> [!NOTE]
>  Dies ist ein erweitertes Feature ausschließlich für Entwicklungszwecke.  
  
 Das folgende Beispiel veranschaulicht, wie Sie festlegen, dass die Runtime in Verzeichnissen, die durch die DEVPATH\-Umgebungsvariable angegeben werden, nach Assemblys sucht.  
  
## Beispiel  
  
```  
<configuration>  
  <runtime>  
    <developmentMode developerInstallation="true"/>  
  </runtime>  
</configuration>  
```  
  
 Diese Einstellung hat den Standardwert **false**.  
  
> [!NOTE]
>  Verwenden Sie diese Einstellung nur zur Entwicklungszeit.  Die Runtime überprüft nicht die Versionen von Assemblys mit starken Namen in DEVPATH.  Sie verwendet einfach die erste Assembly, die sie findet.  
  
## Siehe auch  
 [Configuring .NET Framework Apps](http://msdn.microsoft.com/de-de/d789b592-fcb5-4e3d-8ac9-e0299adaaa42)