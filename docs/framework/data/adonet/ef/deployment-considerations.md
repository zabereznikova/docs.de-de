---
title: Überlegungen zur Bereitstellung (Entity Framework)
ms.date: 03/30/2017
ms.assetid: 3a847a22-4eb8-4565-b18b-453bbca070db
ms.openlocfilehash: 7ab3827a9f2072f6f4b0c34f3801ee5dff2821d3
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59199595"
---
# <a name="deployment-considerations-entity-framework"></a>Überlegungen zur Bereitstellung (Entity Framework)
Dieses Thema enthält Informationen über das Bereitstellen von Anwendungen, die das ADO.NET Entity Framework für den Datenzugriff verwenden. Weitere Informationen über das Entity Framework finden Sie unter [Einstieg](../../../../../docs/framework/data/adonet/ef/getting-started.md).  
  
 Das Entity Framework stellt einen Satz von Tools zur Verfügung, die zur Verwendung in Visual Studio geeignet sind und die Entwicklung in Visual Studio vereinfachen. Weitere Informationen finden Sie unter [ADO.NET Entity Data Model-Tools](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100)). In diesem Thema wird nicht beschrieben, wie spezielle Technologien verwendet werden, um eine Entity Framework-basierte Anwendung bereitzustellen.  
  
 Visual Studio stellt Funktionen zum Verteilen und Bereitstellen von Anwendungen bereit, z. B. die ClickOnce-Bereitstellung. Weitere Informationen finden Sie unter [Bereitstellen von Anwendungen und Komponenten](/visualstudio/deployment/deploying-applications-services-and-components) in Visual Studio-Dokumentation.  
  
 Die folgenden Überlegungen gelten, wenn Sie eine Anwendung bereitstellen, die das Entity Framework verwendet:  
  
-   Das Entity Framework ist seit .NET Framework 3.5 Service Pack 1 (SP1) eine Komponente von .NET Framework. Sie müssen sicherstellen, dass .NET Framework 3.5 SP1 oder eine neuere Version installiert ist, wenn Sie eine Anwendung auf der Grundlage von Entity Framework bereitstellen möchten.  
  
-   Wenn Sie ein konzeptionelles Modell mit dem Entity Data Model-Assistenten erstellen, wird in der Anwendungskonfigurationsdatei eine Verbindungszeichenfolge erstellt. Modell- und Zuordnungsdateien können als Anwendungsressourcen eingebettet oder in das Ausgabeverzeichnis kopiert werden. Standardmäßig werden sie als eingebettete Anwendungsressourcen bereitgestellt. Verwenden Sie die `Metadata Artifact Processing`-Eigenschaft in Entity Designer, um eine dieser Optionen auszuwählen. Weitere Informationen finden Sie unter [Vorgehensweise: Kopieren des Modells und Zuordnungsdateien in das Ausgabeverzeichnis](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc716709(v=vs.100)).  
  
-   Stellen Sie sicher, dass die Modell- und Zuordnungsinformationen (ausgedrückt in konzeptioneller Schemadefinitionssprache (CSDL)), die Datenspeicherschema-Definitionssprache (SSDL) und die Mapping-Spezifikationssprache (MSL) zusammen mit der Anwendung und am von der Verbindungszeichenfolge angegebenen Speicherort bereitgestellt werden. Weitere Informationen finden Sie in [Verbindungszeichenfolgen](../../../../../docs/framework/data/adonet/ef/connection-strings.md).  
  
-   Wenn Sie Modell- und Zuordnungsinformationen als Anwendungsressourcen einbetten, müssen Sie bei jeder Aktualisierung des konzeptionellen Modells die Anwendung neu kompilieren und erneut bereitstellen.  
  
-   Da das Entity Framework eine Komponente von .NET Framework ist, kann es gemäß der .NET Framework-Lizenzvereinbarung mit Ihrer Anwendung weitergegeben werden.  
  
## <a name="see-also"></a>Siehe auch

- [ADO.NET Entity Framework](../../../../../docs/framework/data/adonet/ef/index.md)
- [Überlegungen zur Entwicklung und Bereitstellung](../../../../../docs/framework/data/adonet/ef/development-and-deployment-considerations.md)
