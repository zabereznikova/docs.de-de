---
title: "&#220;berlegungen zur Bereitstellung (Entity Framework) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
ms.assetid: 3a847a22-4eb8-4565-b18b-453bbca070db
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# &#220;berlegungen zur Bereitstellung (Entity Framework)
Dieses Thema enthält Informationen über das Bereitstellen von Anwendungen, die das ADO.NET Entity Framework für den Datenzugriff verwenden.  Weitere Informationen zum Entity Framework finden Sie unter [Erste Schritte](../../../../../docs/framework/data/adonet/ef/getting-started.md).  
  
 Das Entity Framework stellt einen Satz von Tools zur Verfügung, die zur Verwendung in Visual Studio geeignet sind und die Entwicklung in Visual Studio vereinfachen.  Weitere Informationen finden Sie unter [ADO.NET Entity Data Model  Tools](http://msdn.microsoft.com/de-de/91076853-0881-421b-837a-f582f36be527).  In diesem Thema wird nicht beschrieben, wie spezielle Technologien verwendet werden, um eine Entity Framework\-basierte Anwendung bereitzustellen.  
  
 Visual Studio stellt Funktionen zum Verteilen und Bereitstellen von Anwendungen bereit, z. B. die ClickOnce\-Bereitstellung.  Weitere Informationen finden Sie unter [Bereitstellen von Anwendungen und Komponenten](../Topic/Deploying%20Applications,%20Services,%20and%20Components.md) in der Visual Studio\-Dokumentation.  
  
 Die folgenden Überlegungen gelten, wenn Sie eine Anwendung bereitstellen, die das Entity Framework verwendet:  
  
-   Das Entity Framework ist seit .NET Framework 3.5 Service Pack 1 \(SP1\) eine Komponente von .NET Framework.  Sie müssen sicherstellen, dass .NET Framework 3.5 SP1 oder eine neuere Version installiert ist, wenn Sie eine Anwendung auf der Grundlage von Entity Framework bereitstellen möchten.  
  
-   Wenn Sie ein konzeptionelles Modell mit dem Entity Data Model\-Assistenten erstellen, wird in der Anwendungskonfigurationsdatei eine Verbindungszeichenfolge erstellt.  Modell\- und Zuordnungsdateien können als Anwendungsressourcen eingebettet oder in das Ausgabeverzeichnis kopiert werden.  Standardmäßig werden sie als eingebettete Anwendungsressourcen bereitgestellt.  Verwenden Sie die `Metadata Artifact Processing`\-Eigenschaft in Entity Designer, um eine dieser Optionen auszuwählen.  Weitere Informationen finden Sie unter [How to: Copy Model and Mapping Files to the Output Directory](http://msdn.microsoft.com/de-de/e2c9820f-1705-457e-9fdb-8b289f3179b4).  
  
-   Stellen Sie sicher, dass die Modell\- und Zuordnungsinformationen \(ausgedrückt in konzeptioneller Schemadefinitionssprache \(CSDL\)\), die Datenspeicherschema\-Definitionssprache \(SSDL\) und die Mapping\-Spezifikationssprache \(MSL\) zusammen mit der Anwendung und am von der Verbindungszeichenfolge angegebenen Speicherort bereitgestellt werden.  Weitere Informationen finden Sie unter [Verbindungszeichenfolgen](../../../../../docs/framework/data/adonet/ef/connection-strings.md).  
  
-   Wenn Sie Modell\- und Zuordnungsinformationen als Anwendungsressourcen einbetten, müssen Sie bei jeder Aktualisierung des konzeptionellen Modells die Anwendung neu kompilieren und erneut bereitstellen.  
  
-   Da das Entity Framework eine Komponente von .NET Framework ist, kann es gemäß der .NET Framework\-Lizenzvereinbarung mit Ihrer Anwendung weitergegeben werden.  
  
## Siehe auch  
 [ADO.NET Entity Framework](../../../../../docs/framework/data/adonet/ef/index.md)   
 [Überlegungen zur Entwicklung und Bereitstellung](../../../../../docs/framework/data/adonet/ef/development-and-deployment-considerations.md)