---
title: Überlegungen zur Bereitstellung (Entity Framework)
ms.date: 03/30/2017
ms.assetid: 3a847a22-4eb8-4565-b18b-453bbca070db
ms.openlocfilehash: 034fb48050fb0e6a9aabf6c183f8721f0a7115e4
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91181127"
---
# <a name="deployment-considerations-entity-framework"></a>Überlegungen zur Bereitstellung (Entity Framework)

Dieses Thema enthält Informationen über das Bereitstellen von Anwendungen, die das ADO.NET Entity Framework für den Datenzugriff verwenden. Weitere Informationen zum Entity Framework finden Sie unter [Getting Started](getting-started.md).  
  
 Das Entity Framework stellt einen Satz von Tools zur Verfügung, die zur Verwendung in Visual Studio geeignet sind und die Entwicklung in Visual Studio vereinfachen. Weitere Informationen finden Sie unter [ADO.NET Entity Data Model Tools](/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100)). In diesem Thema wird nicht beschrieben, wie spezielle Technologien verwendet werden, um eine Entity Framework-basierte Anwendung bereitzustellen.  
  
 Visual Studio stellt Funktionen zum Verteilen und Bereitstellen von Anwendungen bereit, z. B. die ClickOnce-Bereitstellung. Weitere Informationen finden Sie unter Bereitstellen von [Anwendungen und Komponenten](/visualstudio/deployment/deploying-applications-services-and-components) in der Visual Studio-Dokumentation.  
  
 Die folgenden Überlegungen gelten, wenn Sie eine Anwendung bereitstellen, die das Entity Framework verwendet:  
  
- Das Entity Framework ist seit .NET Framework 3.5 Service Pack 1 (SP1) eine Komponente von .NET Framework. Sie müssen sicherstellen, dass .NET Framework 3.5 SP1 oder eine neuere Version installiert ist, wenn Sie eine Anwendung auf der Grundlage von Entity Framework bereitstellen möchten.  
  
- Wenn Sie ein konzeptionelles Modell mit dem Entity Data Model-Assistenten erstellen, wird in der Anwendungskonfigurationsdatei eine Verbindungszeichenfolge erstellt. Modell- und Zuordnungsdateien können als Anwendungsressourcen eingebettet oder in das Ausgabeverzeichnis kopiert werden. Standardmäßig werden sie als eingebettete Anwendungsressourcen bereitgestellt. Verwenden Sie die `Metadata Artifact Processing`-Eigenschaft in Entity Designer, um eine dieser Optionen auszuwählen. Weitere Informationen finden Sie unter Gewusst [wie: Kopieren von Modell-und Mapping-Dateien in das Ausgabeverzeichnis](/previous-versions/dotnet/netframework-4.0/cc716709(v=vs.100)).  
  
- Stellen Sie sicher, dass die Modell- und Zuordnungsinformationen (ausgedrückt in konzeptioneller Schemadefinitionssprache (CSDL)), die Datenspeicherschema-Definitionssprache (SSDL) und die Mapping-Spezifikationssprache (MSL) zusammen mit der Anwendung und am von der Verbindungszeichenfolge angegebenen Speicherort bereitgestellt werden. Weitere Informationen finden Sie unter [Verbindungs](connection-strings.md)Zeichenfolgen.  
  
- Wenn Sie Modell- und Zuordnungsinformationen als Anwendungsressourcen einbetten, müssen Sie bei jeder Aktualisierung des konzeptionellen Modells die Anwendung neu kompilieren und erneut bereitstellen.  
  
- Da das Entity Framework eine Komponente von .NET Framework ist, kann es gemäß der .NET Framework-Lizenzvereinbarung mit Ihrer Anwendung weitergegeben werden.  
  
## <a name="see-also"></a>Weitere Informationen

- [ADO.NET Entity Framework](index.md)
- [Überlegungen zur Entwicklung und Bereitstellung](development-and-deployment-considerations.md)
