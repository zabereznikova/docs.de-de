---
title: 'Vorgehensweise: Zuordnen von Vererbungshierarchien'
ms.date: 03/30/2017
ms.assetid: b27c779b-9355-4dc7-b95f-7dfd504b6e48
dev_langs:
- csharp
- vb
ms.openlocfilehash: 1366e8f5f79a8e695e52c405e20a894861453ae7
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70781768"
---
# <a name="how-to-map-inheritance-hierarchies"></a>Vorgehensweise: Zuordnen von Vererbungshierarchien
Zur Implementierung dieser Zuordnung in [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] müssen Sie die Attribute in der Stammklasse der Vererbungshierarchie angeben. Führen Sie dazu die folgenden Schritte aus. Entwickler, die Visual Studio verwenden, können den objektrelationaler Designer verwenden, um Vererbungs Hierarchien zuzuordnen. Weitere Informationen finden Sie unter [How to: Configure inheritance by using the O/R Designer (Vorgehensweise: Konfigurieren der Vererbung mit dem O/R-Designer)](/visualstudio/data-tools/how-to-configure-inheritance-by-using-the-o-r-designer).  
  
> [!NOTE]
> Für Unterklassen sind keine besonderen Attribute oder Eigenschaften erforderlich. Beachten Sie besonders, dass Unterklassen nicht über das <xref:System.Data.Linq.Mapping.TableAttribute>-Attribut verfügen.  
  
### <a name="to-map-an-inheritance-hierarchy"></a>So ordnen Sie eine Vererbungshierarchie zu  
  
1. Fügen Sie der Stammklasse das <xref:System.Data.Linq.Mapping.TableAttribute>-Attribut hinzu.  
  
2. Fügen Sie der Stammklasse ein <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute>-Attribut für jede Klasse in der Hierarchiestruktur hinzu.  
  
3. Definieren Sie für jedes <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute>-Attribut eine <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute.Code%2A>-Eigenschaft.  
  
     Diese Eigenschaft enthält einen Wert, der in der Datenbanktabelle in der <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDiscriminator%2A>-Spalte erscheint, um anzugeben, zu welcher Klasse oder Unterklasse diese Datenzeile gehört.  
  
4. Fügen Sie auch für jedes <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute>-Attribut eine <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute.Type%2A>-Eigenschaft hinzu.  
  
     Diese Eigenschaft enthält einen Wert, der angibt, welche Klasse oder Unterklasse der Schlüsselwert darstellt.  
  
5. Fügen Sie nur für eines der <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute>-Attribute eine <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute.IsDefault%2A>-Eigenschaft hinzu.  
  
     Diese Eigenschaft dient zum Festlegen einer *Fall Back* Zuordnung, wenn der Diskriminatorwert aus der Datenbanktabelle keinem <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute.Code%2A> Wert in den Vererbungs Zuordnungen entspricht.  
  
6. Fügen Sie eine <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDiscriminator%2A>-Eigenschaft für ein <xref:System.Data.Linq.Mapping.ColumnAttribute>-Attribut hinzu.  
  
     Diese Eigenschaft gibt an, dass dies die Spalte ist, die den <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute.Code%2A>-Wert enthält.  
  
## <a name="example"></a>Beispiel  
  
> [!NOTE]
> Wenn Sie Visual Studio verwenden, können Sie das objektrelationaler Designer verwenden, um die Vererbung zu konfigurieren. Weitere Informationen finden Sie unter [How to: Konfigurieren der Vererbung mit dem O/R-Designer](/visualstudio/data-tools/how-to-configure-inheritance-by-using-the-o-r-designer)  
  
 Im folgenden Codebeispiel ist `Vehicle` als Stammklasse definiert, und die vorherigen Schritte wurden implementiert, um die Hierarchie für [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] zu beschreiben.  
  
 [!code-csharp[DLinqCustomize#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCustomize/cs/Program.cs#4)]
 [!code-vb[DLinqCustomize#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCustomize/vb/Module1.vb#4)]  
  
## <a name="see-also"></a>Siehe auch

- [Unterstützung von Vererbung](inheritance-support.md)
- [Vorgehensweise: Anpassen von Entitäts Klassen mit dem Code-Editor](how-to-customize-entity-classes-by-using-the-code-editor.md)
