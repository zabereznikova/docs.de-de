---
title: 'Vorgehensweise: Aktivieren der Serialisierbarkeit von Entitäten'
ms.date: 03/30/2017
ms.assetid: a6c5bf6e-064a-4f77-b74c-76b3a5dec309
ms.openlocfilehash: 40a0b4d5a49f88af1bedcbefdd117f6c000b791d
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70793566"
---
# <a name="how-to-make-entities-serializable"></a>Vorgehensweise: Aktivieren der Serialisierbarkeit von Entitäten
Sie können die Serialisierbarkeit von Entitäten aktivieren, wenn Sie den Code generieren. Entitätsklassen werden mit dem <xref:System.Runtime.Serialization.DataContractAttribute>-Attribut und Spalten mit dem <xref:System.Runtime.Serialization.DataMemberAttribute>-Attribut ergänzt.  
  
 Entwickler, die Visual Studio verwenden, können die objektrelationaler Designer zu diesem Zweck verwenden.  
  
 Wenn Sie das SQLMetal-Befehlszeilen Tool verwenden, verwenden Sie die **/Serialization** -Option mit `unidirectional` dem-Argument. Weitere Informationen finden Sie unter [SqlMetal.exe (Tool zur Codegenerierung)](../../../../tools/sqlmetal-exe-code-generation-tool.md).  
  
## <a name="example"></a>Beispiel  
 Die folgenden SQLMetal-Befehlszeilen erzeugen Dateien, die serialisierbare Entitäten aufweisen.  
  
```  
sqlmetal /code:nwserializable.vb /language:vb "c:\northwnd.mdf" /sprocs /functions /pluralize /serialization:unidirectional  
```  
  
```  
sqlmetal /code:nwserializable.cs /language:csharp "c:\northwnd.mdf" /sprocs /functions /pluralize /serialization:unidirectional  
```  
  
## <a name="see-also"></a>Siehe auch

- [Serialisierung](serialization.md)
- [Erstellen des Objektmodells](creating-the-object-model.md)
