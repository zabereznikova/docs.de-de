---
title: 'Vorgehensweise: Bereitstellen von Modell- und Zuordnungsdateien als eingebettete Ressourcen'
ms.date: 03/30/2017
ms.assetid: 20dfae4d-e95a-4264-9540-f5ad23b462d3
ms.openlocfilehash: c88e0c09742d76c7508d7d782eabbe46035d3501
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251450"
---
# <a name="how-to-make-model-and-mapping-files-embedded-resources"></a>Vorgehensweise: Bereitstellen von Modell- und Zuordnungsdateien als eingebettete Ressourcen
Mit [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] können Sie Modell-und Zuordnungsdateien als eingebettete Ressourcen einer Anwendung bereitstellen. Die Assembly mit den eingebetteten Modell- und Zuordnungsdatendateien muss in derselben Anwendungsdomäne geladen werden wie die Entitätsverbindung. Weitere Informationen finden Sie in [Verbindungszeichenfolgen](connection-strings.md). Standardmäßig Betten die Entity Data Model Tools die Modell-und Mapping-Dateien ein. Wenn Sie die Modell- und Zuordnungsdateien manuell definieren, verwenden Sie diese Prozedur, um sicherzustellen, dass die Dateien als eingebettete Ressourcen zusammen mit einer [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]-Anwendung bereitgestellt werden.  
  
> [!NOTE]
> Wiederholen Sie diese Prozedur, wenn Modell- und Zuordnungsdateien geändert werden, um eingebettete Ressourcen beizubehalten.  
  
### <a name="to-embed-model-and-mapping-files"></a>So betten Sie Modell- und Zuordnungsdateien ein  
  
1. Wählen Sie in **Projektmappen-Explorer**die konzeptionelle Datei (. CSDL) aus.  
  
2. Legen Sie im Bereich **Eigenschaften** die **Eigenschaft** Buildvorgang auf **eingebettete Ressource**fest.  
  
3. Wiederholen Sie die Schritte 1 und 2 für die SSDL-Speicherdatei und die MSL-Zuordnungsdatei.  
  
4. Doppelklicken Sie in **Projektmappen-Explorer**auf die Datei app. config, und ändern Sie `Metadata` dann den Parameter `connectionString` im-Attribut basierend auf einem der folgenden Formate:  
  
    - `Metadata=` `res://<assemblyFullName>/<resourceName>;`  
  
    - `Metadata=` `res://*/<resourceName>;`  
  
    - `Metadata=res://*;`  
  
     Weitere Informationen finden Sie in [Verbindungszeichenfolgen](connection-strings.md).  
  
## <a name="example"></a>Beispiel  
 Die folgende Verbindungs Zeichenfolge verweist auf eingebettete Modell-und Mapping-Dateien für das [AdventureWorks Sales-Modell](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks). Diese Verbindungszeichenfolge wird in der Datei App.config des Projekts gespeichert.  

## <a name="see-also"></a>Siehe auch

- [Modellieren und Zuordnen](modeling-and-mapping.md)
- [Vorgehensweise: Definieren der Verbindungs Zeichenfolge](how-to-define-the-connection-string.md)
- [Vorgehensweise: Erstellen einer EntityConnection-Verbindungs Zeichenfolge](how-to-build-an-entityconnection-connection-string.md)
- [ADO.NET-Entity Data Model Tools](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))
