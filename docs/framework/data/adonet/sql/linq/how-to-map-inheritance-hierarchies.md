---
title: "Vorgehensweise: Zuordnen von Vererbungshierarchien | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: b27c779b-9355-4dc7-b95f-7dfd504b6e48
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# Vorgehensweise: Zuordnen von Vererbungshierarchien
Zur Implementierung dieser Zuordnung in [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] müssen Sie die Attribute in der Stammklasse der Vererbungshierarchie angeben. Führen Sie dazu die folgenden Schritte aus.  Entwickler mit [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] können Vererbungshierarchien mithilfe des [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] zuordnen.  Weitere Informationen finden Sie unter [Vorgehensweise: Konfigurieren von Vererbung mit dem O\/R\-Designer](../Topic/How%20to:%20Configure%20inheritance%20by%20using%20the%20O-R%20Designer.md).  
  
> [!NOTE]
>  Für Unterklassen sind keine besonderen Attribute oder Eigenschaften erforderlich.  Beachten Sie besonders, dass Unterklassen nicht über das <xref:System.Data.Linq.Mapping.TableAttribute>\-Attribut verfügen.  
  
### So ordnen Sie eine Vererbungshierarchie zu  
  
1.  Fügen Sie der Stammklasse das <xref:System.Data.Linq.Mapping.TableAttribute>\-Attribut hinzu.  
  
2.  Fügen Sie der Stammklasse ein <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute>\-Attribut für jede Klasse in der Hierarchiestruktur hinzu.  
  
3.  Definieren Sie für jedes <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute>\-Attribut eine <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute.Code%2A>\-Eigenschaft.  
  
     Diese Eigenschaft enthält einen Wert, der in der Datenbanktabelle in der <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDiscriminator%2A>\-Spalte erscheint, um anzugeben, zu welcher Klasse oder Unterklasse diese Datenzeile gehört.  
  
4.  Fügen Sie auch für jedes <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute>\-Attribut eine <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute.Type%2A>\-Eigenschaft hinzu.  
  
     Diese Eigenschaft enthält einen Wert, der angibt, welche Klasse oder Unterklasse der Schlüsselwert darstellt.  
  
5.  Fügen Sie nur für eines der <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute>\-Attribute eine <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute.IsDefault%2A>\-Eigenschaft hinzu.  
  
     Diese Eigenschaft dient der Kennzeichnung einer *Rückzugszuordnung*, wenn der Diskriminatorwert aus der Datenbanktabelle mit keinem der <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute.Code%2A>\-Werte in den Vererbungshierarchien übereinstimmt.  
  
6.  Fügen Sie eine <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDiscriminator%2A>\-Eigenschaft für ein <xref:System.Data.Linq.Mapping.ColumnAttribute>\-Attribut hinzu.  
  
     Diese Eigenschaft gibt an, dass dies die Spalte ist, die den <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute.Code%2A>\-Wert enthält.  
  
## Beispiel  
  
> [!NOTE]
>  Wenn Sie [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] verwenden, können Sie mit dem [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] die Vererbung konfigurieren.  Weitere Informationen finden Sie unter [Vorgehensweise: Konfigurieren von Vererbung mit dem O\/R\-Designer](../Topic/How%20to:%20Configure%20inheritance%20by%20using%20the%20O-R%20Designer.md).  
  
 Im folgenden Codebeispiel ist `Vehicle` als Stammklasse definiert, und die vorherigen Schritte wurden implementiert, um die Hierarchie für [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] zu beschreiben.  
  
 [!code-csharp[DLinqCustomize#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCustomize/cs/Program.cs#4)]
 [!code-vb[DLinqCustomize#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCustomize/vb/Module1.vb#4)]  
  
## Siehe auch  
 [Vererbungsunterstützung](../../../../../../docs/framework/data/adonet/sql/linq/inheritance-support.md)   
 [Vorgehensweise: Anpassen von Entitätsklassen mithilfe des Code\-Editors](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)