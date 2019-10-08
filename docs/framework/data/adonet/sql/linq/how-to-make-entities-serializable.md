---
title: 'Vorgehensweise: Aktivieren der Serialisierbarkeit von Entitäten'
ms.date: 03/30/2017
ms.assetid: a6c5bf6e-064a-4f77-b74c-76b3a5dec309
ms.openlocfilehash: 5e9d078ed2daacfa48b09693f533e9aade613281
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/07/2019
ms.locfileid: "72002712"
---
# <a name="how-to-make-entities-serializable"></a>Vorgehensweise: Aktivieren der Serialisierbarkeit von Entitäten
Sie können die Serialisierbarkeit von Entitäten aktivieren, wenn Sie den Code generieren. Entitätsklassen werden mit dem <xref:System.Runtime.Serialization.DataContractAttribute>-Attribut und Spalten mit dem <xref:System.Runtime.Serialization.DataMemberAttribute>-Attribut ergänzt.  
  
 Entwickler, die Visual Studio verwenden, können die objektrelationaler Designer zu diesem Zweck verwenden.  
  
 Wenn Sie das SQLMetal-Befehlszeilen Tool verwenden, verwenden Sie die **/Serialization** -Option mit dem Argument `unidirectional`. Weitere Informationen finden Sie unter [SqlMetal.exe (Tool zur Codegenerierung)](../../../../tools/sqlmetal-exe-code-generation-tool.md).  
  
## <a name="example"></a>Beispiel  
 Die folgenden SQLMetal-Befehlszeilen erzeugen Dateien, die serialisierbare Entitäten aufweisen.  
  
```console  
sqlmetal /code:nwserializable.vb /language:vb "c:\northwnd.mdf" /sprocs /functions /pluralize /serialization:unidirectional  
```  
  
```console  
sqlmetal /code:nwserializable.cs /language:csharp "c:\northwnd.mdf" /sprocs /functions /pluralize /serialization:unidirectional  
```  
  
## <a name="see-also"></a>Siehe auch

- [Serialisierung](serialization.md)
- [Erstellen des Objektmodells](creating-the-object-model.md)
