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
# <a name="how-to-make-entities-serializable"></a><span data-ttu-id="2b6ce-102">Vorgehensweise: Aktivieren der Serialisierbarkeit von Entitäten</span><span class="sxs-lookup"><span data-stu-id="2b6ce-102">How to: Make Entities Serializable</span></span>
<span data-ttu-id="2b6ce-103">Sie können die Serialisierbarkeit von Entitäten aktivieren, wenn Sie den Code generieren.</span><span class="sxs-lookup"><span data-stu-id="2b6ce-103">You can make entities serializable when you generate your code.</span></span> <span data-ttu-id="2b6ce-104">Entitätsklassen werden mit dem <xref:System.Runtime.Serialization.DataContractAttribute>-Attribut und Spalten mit dem <xref:System.Runtime.Serialization.DataMemberAttribute>-Attribut ergänzt.</span><span class="sxs-lookup"><span data-stu-id="2b6ce-104">Entity classes are decorated with the <xref:System.Runtime.Serialization.DataContractAttribute> attribute, and columns with the <xref:System.Runtime.Serialization.DataMemberAttribute> attribute.</span></span>  
  
 <span data-ttu-id="2b6ce-105">Entwickler, die Visual Studio verwenden, können die objektrelationaler Designer zu diesem Zweck verwenden.</span><span class="sxs-lookup"><span data-stu-id="2b6ce-105">Developers using Visual Studio can use the Object Relational Designer for this purpose.</span></span>  
  
 <span data-ttu-id="2b6ce-106">Wenn Sie das SQLMetal-Befehlszeilen Tool verwenden, verwenden Sie die **/Serialization** -Option mit dem Argument `unidirectional`.</span><span class="sxs-lookup"><span data-stu-id="2b6ce-106">If you are using the SQLMetal command-line tool, use the **/serialization** option with the `unidirectional` argument.</span></span> <span data-ttu-id="2b6ce-107">Weitere Informationen finden Sie unter [SqlMetal.exe (Tool zur Codegenerierung)](../../../../tools/sqlmetal-exe-code-generation-tool.md).</span><span class="sxs-lookup"><span data-stu-id="2b6ce-107">For more information, see [SqlMetal.exe (Code Generation Tool)](../../../../tools/sqlmetal-exe-code-generation-tool.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="2b6ce-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="2b6ce-108">Example</span></span>  
 <span data-ttu-id="2b6ce-109">Die folgenden SQLMetal-Befehlszeilen erzeugen Dateien, die serialisierbare Entitäten aufweisen.</span><span class="sxs-lookup"><span data-stu-id="2b6ce-109">The following SQLMetal command lines produce files that have serializable entities.</span></span>  
  
```console  
sqlmetal /code:nwserializable.vb /language:vb "c:\northwnd.mdf" /sprocs /functions /pluralize /serialization:unidirectional  
```  
  
```console  
sqlmetal /code:nwserializable.cs /language:csharp "c:\northwnd.mdf" /sprocs /functions /pluralize /serialization:unidirectional  
```  
  
## <a name="see-also"></a><span data-ttu-id="2b6ce-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2b6ce-110">See also</span></span>

- [<span data-ttu-id="2b6ce-111">Serialisierung</span><span class="sxs-lookup"><span data-stu-id="2b6ce-111">Serialization</span></span>](serialization.md)
- [<span data-ttu-id="2b6ce-112">Erstellen des Objektmodells</span><span class="sxs-lookup"><span data-stu-id="2b6ce-112">Creating the Object Model</span></span>](creating-the-object-model.md)
