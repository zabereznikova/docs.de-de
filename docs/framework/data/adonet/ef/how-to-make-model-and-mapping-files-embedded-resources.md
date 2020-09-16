---
title: 'Vorgehensweise: Bereitstellen von Modell- und Zuordnungsdateien als eingebettete Ressourcen'
ms.date: 03/30/2017
ms.assetid: 20dfae4d-e95a-4264-9540-f5ad23b462d3
ms.openlocfilehash: aaab2ccc96497cb718b868f7ac63995ad4ba35c8
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90546678"
---
# <a name="how-to-make-model-and-mapping-files-embedded-resources"></a>Vorgehensweise: Bereitstellen von Modell- und Zuordnungsdateien als eingebettete Ressourcen
Mit der Entity Framework können Sie Modell-und Zuordnungsdateien als eingebettete Ressourcen einer Anwendung bereitstellen. Die Assembly mit den eingebetteten Modell- und Zuordnungsdatendateien muss in derselben Anwendungsdomäne geladen werden wie die Entitätsverbindung. Weitere Informationen finden Sie unter [Verbindungs](connection-strings.md)Zeichenfolgen. Standardmäßig Betten die Entity Data Model Tools die Modell-und Mapping-Dateien ein. Wenn Sie die Modell-und Zuordnungsdateien manuell definieren, verwenden Sie dieses Verfahren, um sicherzustellen, dass die Dateien als eingebettete Ressourcen in Verbindung mit einer Entity Framework Anwendung bereitgestellt werden.  
  
> [!NOTE]
> Wiederholen Sie diese Prozedur, wenn Modell- und Zuordnungsdateien geändert werden, um eingebettete Ressourcen beizubehalten.  
  
### <a name="to-embed-model-and-mapping-files"></a>So betten Sie Modell- und Zuordnungsdateien ein  
  
1. Wählen Sie in **Projektmappen-Explorer**die konzeptionelle Datei (. CSDL) aus.  
  
2. Legen Sie im Bereich **Eigenschaften** die **Eigenschaft** Buildvorgang auf **eingebettete Ressource**fest.  
  
3. Wiederholen Sie die Schritte 1 und 2 für die SSDL-Speicherdatei und die MSL-Zuordnungsdatei.  
  
4. Doppelklicken Sie in **Projektmappen-Explorer**auf die Datei App.config, und ändern Sie dann den `Metadata` Parameter im- `connectionString` Attribut basierend auf einem der folgenden Formate:  
  
    - `Metadata=` `res://<assemblyFullName>/<resourceName>;`  
  
    - `Metadata=` `res://*/<resourceName>;`  
  
    - `Metadata=res://*;`  
  
     Weitere Informationen finden Sie unter [Verbindungs](connection-strings.md)Zeichenfolgen.  
  
## <a name="example"></a>Beispiel  
 Die folgende Verbindungs Zeichenfolge verweist auf eingebettete Modell-und Mapping-Dateien für das [AdventureWorks Sales-Modell](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks). Diese Verbindungszeichenfolge wird in der Datei App.config des Projekts gespeichert.  

## <a name="see-also"></a>Siehe auch

- [Modellieren und Zuordnen](modeling-and-mapping.md)
- [Vorgehensweise: Definieren der Verbindungszeichenfolge](how-to-define-the-connection-string.md)
- [Vorgehensweise: Erstellen einer EntityConnection-Verbindungszeichenfolge](how-to-build-an-entityconnection-connection-string.md)
- [ADO.NET-Entity Data Model Tools](/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))
