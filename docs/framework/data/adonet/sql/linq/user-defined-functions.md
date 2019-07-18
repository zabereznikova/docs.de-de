---
title: Benutzerdefinierte Funktionen
ms.date: 03/30/2017
ms.assetid: 3304c9b2-5c7a-4a95-9d45-4f260dcb606e
ms.openlocfilehash: 54faca27e3f70283144f902e531e2a08e45bae3b
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67742712"
---
# <a name="user-defined-functions"></a>Benutzerdefinierte Funktionen
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] verwendet Methoden in Ihrem Objektmodell, die benutzerdefinierte Funktionen darstellen. Sie definieren die Methoden als Funktionen, indem Sie das <xref:System.Data.Linq.Mapping.FunctionAttribute>-Attribut und bei Bedarf auch das <xref:System.Data.Linq.Mapping.ParameterAttribute>-Attribut anwenden. Weitere Informationen finden Sie unter [das LINQ to SQL-Objektmodell](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md).  
  
 Zur Vermeidung einer <xref:System.InvalidOperationException> müssen benutzerdefinierte Funktionen in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] in einer der folgenden Formen vorliegen:  
  
- Eine als Methodenaufruf eingebundene Funktion, die über die richtigen Zuordnungsattribute verfügt. Weitere Informationen finden Sie unter [attributbasierte Zuordnung](../../../../../../docs/framework/data/adonet/sql/linq/attribute-based-mapping.md).  
  
- Eine spezifische statische SQL-Methode für [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].  
  
- Eine Funktion, die von einer .NET Framework-Methode unterstützt wird.  
  
 Dieser Abschnitt erläutert das Bilden und Aufrufen dieser Methoden in Ihrer Anwendung, wenn Sie den Code selbst schreiben. Entwickler, die mit Visual Studio würde den Object Relational Designer in der Regel verwenden, benutzerdefinierte Funktionen zuordnen.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Vorgehensweise: Verwenden von benutzerdefinierten Skalarwertfunktionen](../../../../../../docs/framework/data/adonet/sql/linq/how-to-use-scalar-valued-user-defined-functions.md)  
 Beschreibt, wie eine Funktion, die Skalarwerte zurückgibt, implementiert wird.  
  
 [Vorgehensweise: Verwenden von benutzerdefinierten Tabellenwertfunktionen](../../../../../../docs/framework/data/adonet/sql/linq/how-to-use-table-valued-user-defined-functions.md)  
 Beschreibt, wie eine Funktion, die Tabellenwerte zurückgibt, implementiert wird.  
  
 [Vorgehensweise: Benutzerdefinierte Funktionen Inline aufrufen](../../../../../../docs/framework/data/adonet/sql/linq/how-to-call-user-defined-functions-inline.md)  
 Erläutert Inline-Funktionsaufrufe und die Ausführungsunterschiede, wenn der Aufruf inline erfolgt.
