---
title: 'Vorgehensweise: Aktivieren der Serialisierbarkeit von Entitäten'
ms.date: 03/30/2017
ms.assetid: a6c5bf6e-064a-4f77-b74c-76b3a5dec309
ms.openlocfilehash: fd687ba5dce16baee063f1d3bb9521c6664988b0
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67743278"
---
# <a name="how-to-make-entities-serializable"></a>Vorgehensweise: Aktivieren der Serialisierbarkeit von Entitäten
Sie können die Serialisierbarkeit von Entitäten aktivieren, wenn Sie den Code generieren. Entitätsklassen werden mit dem <xref:System.Runtime.Serialization.DataContractAttribute>-Attribut und Spalten mit dem <xref:System.Runtime.Serialization.DataMemberAttribute>-Attribut ergänzt.  
  
 Der Object Relational Designer können sich Entwickler, die mithilfe von Visual Studio für diesen Zweck.  
  
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
