---
title: "Gewusst wie: Aktivieren der Serialisierbarkeit von Entitäten"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a6c5bf6e-064a-4f77-b74c-76b3a5dec309
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 8f6121b8548c1909f4680419a1fee8f9848ebc1d
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/17/2018
---
# <a name="how-to-make-entities-serializable"></a><span data-ttu-id="94aff-102">Gewusst wie: Aktivieren der Serialisierbarkeit von Entitäten</span><span class="sxs-lookup"><span data-stu-id="94aff-102">How to: Make Entities Serializable</span></span>
<span data-ttu-id="94aff-103">Sie können die Serialisierbarkeit von Entitäten aktivieren, wenn Sie den Code generieren.</span><span class="sxs-lookup"><span data-stu-id="94aff-103">You can make entities serializable when you generate your code.</span></span> <span data-ttu-id="94aff-104">Entitätsklassen werden mit dem <xref:System.Runtime.Serialization.DataContractAttribute>-Attribut und Spalten mit dem <xref:System.Runtime.Serialization.DataMemberAttribute>-Attribut ergänzt.</span><span class="sxs-lookup"><span data-stu-id="94aff-104">Entity classes are decorated with the <xref:System.Runtime.Serialization.DataContractAttribute> attribute, and columns with the <xref:System.Runtime.Serialization.DataMemberAttribute> attribute.</span></span>  
  
 <span data-ttu-id="94aff-105">Entwickler, die mit [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] arbeiten, können für diesen Zweck den [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] verwenden.</span><span class="sxs-lookup"><span data-stu-id="94aff-105">Developers using [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] can use the [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] for this purpose.</span></span>  
  
 <span data-ttu-id="94aff-106">Wenn Sie das SQLMetal-Befehlszeilentool verwenden, verwenden Sie die **/serialization** -Option mit der `unidirectional` Argument.</span><span class="sxs-lookup"><span data-stu-id="94aff-106">If you are using the SQLMetal command-line tool, use the **/serialization** option with the `unidirectional` argument.</span></span> <span data-ttu-id="94aff-107">Weitere Informationen finden Sie unter [SqlMetal.exe (Tool zur Codegenerierung)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md).</span><span class="sxs-lookup"><span data-stu-id="94aff-107">For more information, see [SqlMetal.exe (Code Generation Tool)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="94aff-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="94aff-108">Example</span></span>  
 <span data-ttu-id="94aff-109">Die folgenden SQLMetal-Befehlszeilen erzeugen Dateien, die serialisierbare Entitäten aufweisen.</span><span class="sxs-lookup"><span data-stu-id="94aff-109">The following SQLMetal command lines produce files that have serializable entities.</span></span>  
  
```  
sqlmetal /code:nwserializable.vb /language:vb "c:\northwnd.mdf" /sprocs /functions /pluralize /serialization:unidirectional  
```  
  
```  
sqlmetal /code:nwserializable.cs /language:csharp "c:\northwnd.mdf" /sprocs /functions /pluralize /serialization:unidirectional  
```  
  
## <a name="see-also"></a><span data-ttu-id="94aff-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="94aff-110">See Also</span></span>  
 [<span data-ttu-id="94aff-111">Serialisierung</span><span class="sxs-lookup"><span data-stu-id="94aff-111">Serialization</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/serialization.md)  
 [<span data-ttu-id="94aff-112">Erstellen des Objektmodells</span><span class="sxs-lookup"><span data-stu-id="94aff-112">Creating the Object Model</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/creating-the-object-model.md)
