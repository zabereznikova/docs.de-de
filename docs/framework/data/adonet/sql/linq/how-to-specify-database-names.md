---
title: 'Vorgehensweise: Angeben von Datenbanknamen'
ms.date: 03/30/2017
ms.assetid: b80f0fd2-7f75-45fe-9e12-496f80f183df
ms.openlocfilehash: 82cb3f8f31af433b0299b4fec742b548d61921e4
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91197156"
---
# <a name="how-to-specify-database-names"></a>Vorgehensweise: Angeben von Datenbanknamen

Verwenden Sie die <xref:System.Data.Linq.Mapping.DatabaseAttribute.Name%2A>-Eigenschaft für ein <xref:System.Data.Linq.Mapping.DatabaseAttribute>-Attribut, um den Namen einer Datenbank anzugeben, wenn dieser nicht von der Verbindung bereitgestellt wird.  
  
 Codebeispiele finden Sie unter <xref:System.Data.Linq.Mapping.DatabaseAttribute.Name%2A>.  
  
### <a name="to-specify-the-name-of-the-database"></a>So geben Sie den Namen der Datenbank an  
  
1. Fügen Sie das <xref:System.Data.Linq.Mapping.DatabaseAttribute>-Attribut der Klassendeklaration für die Datenbank hinzu.  
  
2. Fügen Sie die <xref:System.Data.Linq.Mapping.DatabaseAttribute.Name%2A>-Eigenschaft dem <xref:System.Data.Linq.Mapping.DatabaseAttribute>-Attribut hinzu.  
  
3. Legen Sie den <xref:System.Data.Linq.Mapping.DatabaseAttribute.Name%2A>-Eigenschaftswert auf den gewünschten Namen fest.  
  
## <a name="see-also"></a>Weitere Informationen

- [Das LINQ to SQL-Objektmodell](the-linq-to-sql-object-model.md)
- [Vorgehensweise: Anpassen von Entitätsklassen mit dem Code-Editor](how-to-customize-entity-classes-by-using-the-code-editor.md)
