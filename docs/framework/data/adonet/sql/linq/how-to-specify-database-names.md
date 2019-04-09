---
title: 'Vorgehensweise: Angeben von Datenbanknamen'
ms.date: 03/30/2017
ms.assetid: b80f0fd2-7f75-45fe-9e12-496f80f183df
ms.openlocfilehash: 1c694678dc3a60cf91dea62f2a17973b396e2b19
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59184521"
---
# <a name="how-to-specify-database-names"></a><span data-ttu-id="f17b9-102">Vorgehensweise: Angeben von Datenbanknamen</span><span class="sxs-lookup"><span data-stu-id="f17b9-102">How to: Specify Database Names</span></span>
<span data-ttu-id="f17b9-103">Verwenden Sie die <xref:System.Data.Linq.Mapping.DatabaseAttribute.Name%2A>-Eigenschaft für ein <xref:System.Data.Linq.Mapping.DatabaseAttribute>-Attribut, um den Namen einer Datenbank anzugeben, wenn dieser nicht von der Verbindung bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="f17b9-103">Use the <xref:System.Data.Linq.Mapping.DatabaseAttribute.Name%2A> property on a <xref:System.Data.Linq.Mapping.DatabaseAttribute> attribute to specify the name of a database when a name is not supplied by the connection.</span></span>  
  
 <span data-ttu-id="f17b9-104">Codebeispiele finden Sie unter <xref:System.Data.Linq.Mapping.DatabaseAttribute.Name%2A>.</span><span class="sxs-lookup"><span data-stu-id="f17b9-104">For code samples, see <xref:System.Data.Linq.Mapping.DatabaseAttribute.Name%2A>.</span></span>  
  
### <a name="to-specify-the-name-of-the-database"></a><span data-ttu-id="f17b9-105">So geben Sie den Namen der Datenbank an</span><span class="sxs-lookup"><span data-stu-id="f17b9-105">To specify the name of the database</span></span>  
  
1.  <span data-ttu-id="f17b9-106">Fügen Sie das <xref:System.Data.Linq.Mapping.DatabaseAttribute>-Attribut der Klassendeklaration für die Datenbank hinzu.</span><span class="sxs-lookup"><span data-stu-id="f17b9-106">Add the <xref:System.Data.Linq.Mapping.DatabaseAttribute> attribute to the class declaration for the database.</span></span>  
  
2.  <span data-ttu-id="f17b9-107">Fügen Sie die <xref:System.Data.Linq.Mapping.DatabaseAttribute.Name%2A>-Eigenschaft dem <xref:System.Data.Linq.Mapping.DatabaseAttribute>-Attribut hinzu.</span><span class="sxs-lookup"><span data-stu-id="f17b9-107">Add the <xref:System.Data.Linq.Mapping.DatabaseAttribute.Name%2A> property to the <xref:System.Data.Linq.Mapping.DatabaseAttribute> attribute.</span></span>  
  
3.  <span data-ttu-id="f17b9-108">Legen Sie den <xref:System.Data.Linq.Mapping.DatabaseAttribute.Name%2A>-Eigenschaftswert auf den gewünschten Namen fest.</span><span class="sxs-lookup"><span data-stu-id="f17b9-108">Set the <xref:System.Data.Linq.Mapping.DatabaseAttribute.Name%2A> property value to the name that you want to specify.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f17b9-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f17b9-109">See also</span></span>

- [<span data-ttu-id="f17b9-110">Das LINQ to SQL-Objektmodell</span><span class="sxs-lookup"><span data-stu-id="f17b9-110">The LINQ to SQL Object Model</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)
- [<span data-ttu-id="f17b9-111">Vorgehensweise: Anpassen von Entitätsklassen mit dem Code-Editor</span><span class="sxs-lookup"><span data-stu-id="f17b9-111">How to: Customize Entity Classes by Using the Code Editor</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)
