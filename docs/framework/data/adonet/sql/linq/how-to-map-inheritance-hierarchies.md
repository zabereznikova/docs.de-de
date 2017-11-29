---
title: 'Gewusst wie: Zuordnen von Vererbungshierarchien'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b27c779b-9355-4dc7-b95f-7dfd504b6e48
dev_langs:
- csharp
- vb
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 6a0393d11c949c0bceb6587059cd450113c0ead2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-map-inheritance-hierarchies"></a>Gewusst wie: Zuordnen von Vererbungshierarchien
Zur Implementierung dieser Zuordnung in [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] müssen Sie die Attribute in der Stammklasse der Vererbungshierarchie angeben. Führen Sie dazu die folgenden Schritte aus. Entwickler mit [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] können Vererbungshierarchien mithilfe des [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] zuordnen. Finden Sie unter [Vorgehensweise: Konfigurieren der Vererbung mithilfe des O/R-Designers](/visualstudio/data-tools/how-to-configure-inheritance-by-using-the-o-r-designer).  
  
> [!NOTE]
>  Für Unterklassen sind keine besonderen Attribute oder Eigenschaften erforderlich. Beachten Sie besonders, dass Unterklassen nicht über das <xref:System.Data.Linq.Mapping.TableAttribute>-Attribut verfügen.  
  
### <a name="to-map-an-inheritance-hierarchy"></a>So ordnen Sie eine Vererbungshierarchie zu  
  
1.  Fügen Sie der Stammklasse das <xref:System.Data.Linq.Mapping.TableAttribute>-Attribut hinzu.  
  
2.  Fügen Sie der Stammklasse ein <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute>-Attribut für jede Klasse in der Hierarchiestruktur hinzu.  
  
3.  Definieren Sie für jedes <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute>-Attribut eine <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute.Code%2A>-Eigenschaft.  
  
     Diese Eigenschaft enthält einen Wert, der in der Datenbanktabelle in der <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDiscriminator%2A>-Spalte erscheint, um anzugeben, zu welcher Klasse oder Unterklasse diese Datenzeile gehört.  
  
4.  Fügen Sie auch für jedes <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute>-Attribut eine <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute.Type%2A>-Eigenschaft hinzu.  
  
     Diese Eigenschaft enthält einen Wert, der angibt, welche Klasse oder Unterklasse der Schlüsselwert darstellt.  
  
5.  Fügen Sie nur für eines der <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute>-Attribute eine <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute.IsDefault%2A>-Eigenschaft hinzu.  
  
     Diese Eigenschaft dient zum Festlegen einer *fallback* zuordnen, wenn der Diskriminatorwert aus der Datenbanktabelle entspricht keiner <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute.Code%2A> Wert in den Vererbungshierarchien.  
  
6.  Fügen Sie eine <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDiscriminator%2A>-Eigenschaft für ein <xref:System.Data.Linq.Mapping.ColumnAttribute>-Attribut hinzu.  
  
     Diese Eigenschaft gibt an, dass dies die Spalte ist, die den <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute.Code%2A>-Wert enthält.  
  
## <a name="example"></a>Beispiel  
  
> [!NOTE]
>  Wenn Sie [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] verwenden, können Sie mit dem [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] die Vererbung konfigurieren. Finden Sie unter [Vorgehensweise: Konfigurieren der Vererbung mit dem O/R-Designer](/visualstudio/data-tools/how-to-configure-inheritance-by-using-the-o-r-designer)  
  
 Im folgenden Codebeispiel ist `Vehicle` als Stammklasse definiert, und die vorherigen Schritte wurden implementiert, um die Hierarchie für [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] zu beschreiben.  
  
 [!code-csharp[DLinqCustomize#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCustomize/cs/Program.cs#4)]
 [!code-vb[DLinqCustomize#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCustomize/vb/Module1.vb#4)]  
  
## <a name="see-also"></a>Siehe auch  
 [Unterstützung von Vererbung](../../../../../../docs/framework/data/adonet/sql/linq/inheritance-support.md)  
 [Vorgehensweise: Anpassen von Entitätsklassen mithilfe des Code-Editors](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)
