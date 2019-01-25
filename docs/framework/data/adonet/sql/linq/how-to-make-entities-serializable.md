---
title: 'Vorgehensweise: Aktivieren der Serialisierbarkeit von Entitäten'
ms.date: 03/30/2017
ms.assetid: a6c5bf6e-064a-4f77-b74c-76b3a5dec309
ms.openlocfilehash: 9b4ff81b4a779b474097de1a69e65f4864e08691
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54604213"
---
# <a name="how-to-make-entities-serializable"></a>Vorgehensweise: Aktivieren der Serialisierbarkeit von Entitäten
Sie können die Serialisierbarkeit von Entitäten aktivieren, wenn Sie den Code generieren. Entitätsklassen werden mit dem <xref:System.Runtime.Serialization.DataContractAttribute>-Attribut und Spalten mit dem <xref:System.Runtime.Serialization.DataMemberAttribute>-Attribut ergänzt.  
  
 Können Entwickler mithilfe von Visual Studio die [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] für diesen Zweck.  
  
 Wenn Sie das SQLMetal-Befehlszeilentool verwenden, verwenden Sie die **/serialization** -Option mit der `unidirectional` Argument. Weitere Informationen finden Sie unter [SqlMetal.exe (Tool zur Codegenerierung)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md).  
  
## <a name="example"></a>Beispiel  
 Die folgenden SQLMetal-Befehlszeilen erzeugen Dateien, die serialisierbare Entitäten aufweisen.  
  
```  
sqlmetal /code:nwserializable.vb /language:vb "c:\northwnd.mdf" /sprocs /functions /pluralize /serialization:unidirectional  
```  
  
```  
sqlmetal /code:nwserializable.cs /language:csharp "c:\northwnd.mdf" /sprocs /functions /pluralize /serialization:unidirectional  
```  
  
## <a name="see-also"></a>Siehe auch
- [Serialisierung](../../../../../../docs/framework/data/adonet/sql/linq/serialization.md)
- [Erstellen des Objektmodells](../../../../../../docs/framework/data/adonet/sql/linq/creating-the-object-model.md)
