---
title: Überlegungen zur Bereitstellung (Entity Framework)
ms.date: 03/30/2017
ms.assetid: 3a847a22-4eb8-4565-b18b-453bbca070db
ms.openlocfilehash: 4456a466a7b76c68b3185bf586494f8591440844
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="deployment-considerations-entity-framework"></a>Überlegungen zur Bereitstellung (Entity Framework)
Dieses Thema enthält Informationen über das Bereitstellen von Anwendungen, die das ADO.NET Entity Framework für den Datenzugriff verwenden. Weitere Informationen über das Entity Framework finden Sie unter [Einstieg](../../../../../docs/framework/data/adonet/ef/getting-started.md).  
  
 Das Entity Framework stellt einen Satz von Tools zur Verfügung, die zur Verwendung in Visual Studio geeignet sind und die Entwicklung in Visual Studio vereinfachen. Weitere Informationen finden Sie unter [ADO.NET Entity Data Model Tools](http://msdn.microsoft.com/library/91076853-0881-421b-837a-f582f36be527). In diesem Thema wird nicht beschrieben, wie spezielle Technologien verwendet werden, um eine Entity Framework-basierte Anwendung bereitzustellen.  
  
 Visual Studio stellt Funktionen zum Verteilen und Bereitstellen von Anwendungen bereit, z. B. die ClickOnce-Bereitstellung. Weitere Informationen finden Sie unter [Bereitstellen von Anwendungen und Komponenten](/visualstudio/deployment/deploying-applications-services-and-components) in der Visual Studio-Dokumentation.  
  
 Die folgenden Überlegungen gelten, wenn Sie eine Anwendung bereitstellen, die das Entity Framework verwendet:  
  
-   Das Entity Framework ist seit .NET Framework 3.5 Service Pack 1 (SP1) eine Komponente von .NET Framework. Sie müssen sicherstellen, dass .NET Framework 3.5 SP1 oder eine neuere Version installiert ist, wenn Sie eine Anwendung auf der Grundlage von Entity Framework bereitstellen möchten.  
  
-   Wenn Sie ein konzeptionelles Modell mit dem Entity Data Model-Assistenten erstellen, wird in der Anwendungskonfigurationsdatei eine Verbindungszeichenfolge erstellt. Modell- und Zuordnungsdateien können als Anwendungsressourcen eingebettet oder in das Ausgabeverzeichnis kopiert werden. Standardmäßig werden sie als eingebettete Anwendungsressourcen bereitgestellt. Verwenden Sie die `Metadata Artifact Processing`-Eigenschaft in Entity Designer, um eine dieser Optionen auszuwählen. Weitere Informationen finden Sie unter [Vorgehensweise: Kopieren Sie Modell- und Zuordnen von Dateien in das Ausgabeverzeichnis](http://msdn.microsoft.com/library/e2c9820f-1705-457e-9fdb-8b289f3179b4).  
  
-   Stellen Sie sicher, dass die Modell- und Zuordnungsinformationen (ausgedrückt in konzeptioneller Schemadefinitionssprache (CSDL)), die Datenspeicherschema-Definitionssprache (SSDL) und die Mapping-Spezifikationssprache (MSL) zusammen mit der Anwendung und am von der Verbindungszeichenfolge angegebenen Speicherort bereitgestellt werden. Weitere Informationen finden Sie in [Verbindungszeichenfolgen](../../../../../docs/framework/data/adonet/ef/connection-strings.md).  
  
-   Wenn Sie Modell- und Zuordnungsinformationen als Anwendungsressourcen einbetten, müssen Sie bei jeder Aktualisierung des konzeptionellen Modells die Anwendung neu kompilieren und erneut bereitstellen.  
  
-   Da das Entity Framework eine Komponente von .NET Framework ist, kann es gemäß der .NET Framework-Lizenzvereinbarung mit Ihrer Anwendung weitergegeben werden.  
  
## <a name="see-also"></a>Siehe auch  
 [ADO.NET Entity Framework](../../../../../docs/framework/data/adonet/ef/index.md)  
 [Überlegungen zur Entwicklung und Bereitstellung](../../../../../docs/framework/data/adonet/ef/development-and-deployment-considerations.md)
