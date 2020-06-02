---
title: Aufrufen von Funktionen in LINQ to Entities-Abfragen
description: Verwenden Sie diese Artikel, um zu erfahren, wie die Klassen EntityFunctions und SqlFunctions Zugriff auf kanonische Funktionen und Datenbankfunktionen als Teil der Entity Framework bereitstellen.
ms.date: 03/30/2017
ms.assetid: 12a525a9-727c-4464-a0c7-71a0ef541792
ms.openlocfilehash: faa6406713592f10e5e7371cd73f29bec4b03b7b
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "84286856"
---
# <a name="calling-functions-in-linq-to-entities-queries"></a>Aufrufen von Funktionen in LINQ to Entities-Abfragen
In den Themen in diesem Abschnitt wird beschrieben, wie Funktionen in LINQ to Entities-Abfragen aufgerufen werden.  
  
 Die <xref:System.Data.Objects.EntityFunctions>-Klasse und die <xref:System.Data.Objects.SqlClient.SqlFunctions>-Klasse bieten im Rahmen des Entity Framework Zugriff auf kanonische Funktionen und Datenbankfunktionen. Weitere Informationen finden Sie unter Gewusst [wie: Abrufen von kanonischen Funktionen](how-to-call-canonical-functions.md) und Gewusst [wie: Abrufen von Datenbankfunktionen](how-to-call-database-functions.md).  
  
 Zum Aufrufen einer benutzerdefinierten Funktion sind drei grundlegende Schritte erforderlich:  
  
1. Definieren Sie im konzeptionellen Modell eine Funktion, oder deklarieren Sie im Speichermodell eine Funktion.  
  
2. Fügen Sie der Anwendung eine Methode hinzu, und ordnen Sie es mit einem <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute> der Funktion im Modell zu.  
  
3. Rufen Sie die Funktion in einer LINQ to Entities-Abfrage auf.  
  
 Weitere Informationen hierzu finden Sie in diesem Abschnitt.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Vorgehensweise: Aufrufen kanonischer Funktionen](how-to-call-canonical-functions.md)  
  
 [Vorgehensweise: Aufrufen von Datenbankfunktionen](how-to-call-database-functions.md)  
  
 [Vorgehensweise: Aufrufen benutzerdefinierter Datenbankfunktionen](how-to-call-custom-database-functions.md)  
  
 [Vorgehensweise: Aufrufen modelldefinierter Funktionen in Abfragen](how-to-call-model-defined-functions-in-queries.md)  
  
 [Vorgehensweise: Aufrufen modelldefinierter Funktionen als Objektmethoden](how-to-call-model-defined-functions-as-object-methods.md)  
  
## <a name="see-also"></a>Siehe auch

- [Abfragen in LINQ to Entities](queries-in-linq-to-entities.md)
- [Kanonische Funktionen](canonical-functions.md)
- [Übersicht über die EDMX-Datei](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc982042(v=vs.100))
- [Gewusst wie: Definieren von benutzerdefinierten Funktionen im konzeptionellen Modell](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/dd456812(v=vs.100))
