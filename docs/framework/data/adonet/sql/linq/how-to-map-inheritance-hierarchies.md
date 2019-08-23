---
title: 'Vorgehensweise: Zuordnen von Vererbungshierarchien'
ms.date: 03/30/2017
ms.assetid: b27c779b-9355-4dc7-b95f-7dfd504b6e48
dev_langs:
- csharp
- vb
ms.openlocfilehash: 618abc8e681a6f43a1054d0ca2cec2fbdec853f5
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69943561"
---
# <a name="how-to-map-inheritance-hierarchies"></a><span data-ttu-id="3b2b0-102">Vorgehensweise: Zuordnen von Vererbungshierarchien</span><span class="sxs-lookup"><span data-stu-id="3b2b0-102">How to: Map Inheritance Hierarchies</span></span>
<span data-ttu-id="3b2b0-103">Zur Implementierung dieser Zuordnung in [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] müssen Sie die Attribute in der Stammklasse der Vererbungshierarchie angeben. Führen Sie dazu die folgenden Schritte aus.</span><span class="sxs-lookup"><span data-stu-id="3b2b0-103">To implement inheritance mapping in [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)], you must specify the attributes and attribute properties on the root class of the inheritance hierarchy as described in the following steps.</span></span> <span data-ttu-id="3b2b0-104">Entwickler, die Visual Studio verwenden, können den objektrelationaler Designer verwenden, um Vererbungs Hierarchien zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="3b2b0-104">Developers using Visual Studio can use the Object Relational Designer to map inheritance hierarchies.</span></span> <span data-ttu-id="3b2b0-105">Weitere Informationen finden Sie unter [How to: Configure inheritance by using the O/R Designer (Vorgehensweise: Konfigurieren der Vererbung mit dem O/R-Designer)](/visualstudio/data-tools/how-to-configure-inheritance-by-using-the-o-r-designer).</span><span class="sxs-lookup"><span data-stu-id="3b2b0-105">See [How to: Configure inheritance by using the O/R Designer](/visualstudio/data-tools/how-to-configure-inheritance-by-using-the-o-r-designer).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3b2b0-106">Für Unterklassen sind keine besonderen Attribute oder Eigenschaften erforderlich.</span><span class="sxs-lookup"><span data-stu-id="3b2b0-106">No special attributes or properties are required on the subclasses.</span></span> <span data-ttu-id="3b2b0-107">Beachten Sie besonders, dass Unterklassen nicht über das <xref:System.Data.Linq.Mapping.TableAttribute>-Attribut verfügen.</span><span class="sxs-lookup"><span data-stu-id="3b2b0-107">Note especially that subclasses do not have the <xref:System.Data.Linq.Mapping.TableAttribute> attribute.</span></span>  
  
### <a name="to-map-an-inheritance-hierarchy"></a><span data-ttu-id="3b2b0-108">So ordnen Sie eine Vererbungshierarchie zu</span><span class="sxs-lookup"><span data-stu-id="3b2b0-108">To map an inheritance hierarchy</span></span>  
  
1. <span data-ttu-id="3b2b0-109">Fügen Sie der Stammklasse das <xref:System.Data.Linq.Mapping.TableAttribute>-Attribut hinzu.</span><span class="sxs-lookup"><span data-stu-id="3b2b0-109">Add the <xref:System.Data.Linq.Mapping.TableAttribute> attribute to the root class.</span></span>  
  
2. <span data-ttu-id="3b2b0-110">Fügen Sie der Stammklasse ein <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute>-Attribut für jede Klasse in der Hierarchiestruktur hinzu.</span><span class="sxs-lookup"><span data-stu-id="3b2b0-110">Also to the root class, add an <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute> attribute for each class in the hierarchy structure.</span></span>  
  
3. <span data-ttu-id="3b2b0-111">Definieren Sie für jedes <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute>-Attribut eine <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute.Code%2A>-Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="3b2b0-111">For each <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute> attribute, define a <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute.Code%2A> property.</span></span>  
  
     <span data-ttu-id="3b2b0-112">Diese Eigenschaft enthält einen Wert, der in der Datenbanktabelle in der <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDiscriminator%2A>-Spalte erscheint, um anzugeben, zu welcher Klasse oder Unterklasse diese Datenzeile gehört.</span><span class="sxs-lookup"><span data-stu-id="3b2b0-112">This property holds a value that appears in the database table in the <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDiscriminator%2A> column to indicate which class or subclass this row of data belongs to.</span></span>  
  
4. <span data-ttu-id="3b2b0-113">Fügen Sie auch für jedes <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute>-Attribut eine <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute.Type%2A>-Eigenschaft hinzu.</span><span class="sxs-lookup"><span data-stu-id="3b2b0-113">For each <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute> attribute, also add a <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute.Type%2A> property.</span></span>  
  
     <span data-ttu-id="3b2b0-114">Diese Eigenschaft enthält einen Wert, der angibt, welche Klasse oder Unterklasse der Schlüsselwert darstellt.</span><span class="sxs-lookup"><span data-stu-id="3b2b0-114">This property holds a value that specifies which class or subclass the key value signifies.</span></span>  
  
5. <span data-ttu-id="3b2b0-115">Fügen Sie nur für eines der <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute>-Attribute eine <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute.IsDefault%2A>-Eigenschaft hinzu.</span><span class="sxs-lookup"><span data-stu-id="3b2b0-115">On only one of the <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute> attributes, add an <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute.IsDefault%2A> property.</span></span>  
  
     <span data-ttu-id="3b2b0-116">Diese Eigenschaft dient zum Festlegen einer *Fall Back* Zuordnung, wenn der Diskriminatorwert aus der Datenbanktabelle keinem <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute.Code%2A> Wert in den Vererbungs Zuordnungen entspricht.</span><span class="sxs-lookup"><span data-stu-id="3b2b0-116">This property serves to designate a *fallback* mapping when the discriminator value from the database table does not match any <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute.Code%2A> value in the inheritance mappings.</span></span>  
  
6. <span data-ttu-id="3b2b0-117">Fügen Sie eine <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDiscriminator%2A>-Eigenschaft für ein <xref:System.Data.Linq.Mapping.ColumnAttribute>-Attribut hinzu.</span><span class="sxs-lookup"><span data-stu-id="3b2b0-117">Add an <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDiscriminator%2A> property for a <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute.</span></span>  
  
     <span data-ttu-id="3b2b0-118">Diese Eigenschaft gibt an, dass dies die Spalte ist, die den <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute.Code%2A>-Wert enthält.</span><span class="sxs-lookup"><span data-stu-id="3b2b0-118">This property signifies that this is the column that holds the <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute.Code%2A> value.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3b2b0-119">Beispiel</span><span class="sxs-lookup"><span data-stu-id="3b2b0-119">Example</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3b2b0-120">Wenn Sie Visual Studio verwenden, können Sie das objektrelationaler Designer verwenden, um die Vererbung zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="3b2b0-120">If you are using Visual Studio, you can use the Object Relational Designer to configure inheritance.</span></span> <span data-ttu-id="3b2b0-121">Weitere Informationen finden Sie unter [How to: Konfigurieren der Vererbung mit dem O/R-Designer](/visualstudio/data-tools/how-to-configure-inheritance-by-using-the-o-r-designer)</span><span class="sxs-lookup"><span data-stu-id="3b2b0-121">See [How to: Configure inheritance by using the O/R Designer](/visualstudio/data-tools/how-to-configure-inheritance-by-using-the-o-r-designer)</span></span>  
  
 <span data-ttu-id="3b2b0-122">Im folgenden Codebeispiel ist `Vehicle` als Stammklasse definiert, und die vorherigen Schritte wurden implementiert, um die Hierarchie für [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] zu beschreiben.</span><span class="sxs-lookup"><span data-stu-id="3b2b0-122">In the following code example, `Vehicle` is defined as the root class, and the previous steps have been implemented to describe the hierarchy for [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)].</span></span>  
  
 [!code-csharp[DLinqCustomize#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCustomize/cs/Program.cs#4)]
 [!code-vb[DLinqCustomize#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCustomize/vb/Module1.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="3b2b0-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3b2b0-123">See also</span></span>

- [<span data-ttu-id="3b2b0-124">Unterstützung von Vererbung</span><span class="sxs-lookup"><span data-stu-id="3b2b0-124">Inheritance Support</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/inheritance-support.md)
- [<span data-ttu-id="3b2b0-125">Vorgehensweise: Anpassen von Entitäts Klassen mit dem Code-Editor</span><span class="sxs-lookup"><span data-stu-id="3b2b0-125">How to: Customize Entity Classes by Using the Code Editor</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)
