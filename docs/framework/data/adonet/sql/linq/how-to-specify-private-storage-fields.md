---
title: 'Gewusst wie: Angeben von privaten Speicherfeldern'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5a40e816-cc6e-43a0-b32a-9caaa0ab6912
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: bdb25f21a94ac6eb521e08688e33903e8891caf4
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/17/2018
---
# <a name="how-to-specify-private-storage-fields"></a><span data-ttu-id="d30de-102">Gewusst wie: Angeben von privaten Speicherfeldern</span><span class="sxs-lookup"><span data-stu-id="d30de-102">How to: Specify Private Storage Fields</span></span>
<span data-ttu-id="d30de-103">Verwenden der [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.DataAttribute.Storage%2A> Eigenschaft auf die <xref:System.Data.Linq.Mapping.DataAttribute> Attribut, um den Namen eines zugrunde liegenden Speicherfelds anzugeben.</span><span class="sxs-lookup"><span data-stu-id="d30de-103">Use the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.DataAttribute.Storage%2A> property on the <xref:System.Data.Linq.Mapping.DataAttribute> attribute to designate the name of an underlying storage field.</span></span>  
  
 <span data-ttu-id="d30de-104">Codebeispiele finden Sie unter <xref:System.Data.Linq.Mapping.DataAttribute.Storage%2A>.</span><span class="sxs-lookup"><span data-stu-id="d30de-104">For code examples, see <xref:System.Data.Linq.Mapping.DataAttribute.Storage%2A>.</span></span>  
  
### <a name="to-specify-the-name-of-an-underlying-storage-field"></a><span data-ttu-id="d30de-105">So geben Sie den Namen eines zugrunde liegenden Speicherfelds an</span><span class="sxs-lookup"><span data-stu-id="d30de-105">To specify the name of an underlying storage field</span></span>  
  
1.  <span data-ttu-id="d30de-106">Fügen Sie die <xref:System.Data.Linq.Mapping.DataAttribute.Storage%2A>-Eigenschaft dem <xref:System.Data.Linq.Mapping.ColumnAttribute>-Attribut hinzu.</span><span class="sxs-lookup"><span data-stu-id="d30de-106">Add the <xref:System.Data.Linq.Mapping.DataAttribute.Storage%2A> property to the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute.</span></span>  
  
2.  <span data-ttu-id="d30de-107">Weisen Sie den Feldnamen als Wert der <xref:System.Data.Linq.Mapping.DataAttribute.Storage%2A>-Eigenschaft zu.</span><span class="sxs-lookup"><span data-stu-id="d30de-107">Assign the name of the field as the value of the <xref:System.Data.Linq.Mapping.DataAttribute.Storage%2A> property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d30de-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d30de-108">See Also</span></span>  
 [<span data-ttu-id="d30de-109">Das LINQ to SQL-Objektmodell</span><span class="sxs-lookup"><span data-stu-id="d30de-109">The LINQ to SQL Object Model</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)  
 [<span data-ttu-id="d30de-110">Vorgehensweise: Anpassen von Entitätsklassen mit dem Code-Editor</span><span class="sxs-lookup"><span data-stu-id="d30de-110">How to: Customize Entity Classes by Using the Code Editor</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)
