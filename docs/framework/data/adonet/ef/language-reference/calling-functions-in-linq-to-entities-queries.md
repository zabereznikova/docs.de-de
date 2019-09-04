---
title: Aufrufen von Funktionen in LINQ to Entities-Abfragen
ms.date: 03/30/2017
ms.assetid: 12a525a9-727c-4464-a0c7-71a0ef541792
ms.openlocfilehash: 267bb393d9e75c66eb18139e8897da34bd86e159
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251264"
---
# <a name="calling-functions-in-linq-to-entities-queries"></a>Aufrufen von Funktionen in LINQ to Entities-Abfragen
In den Themen in diesem Abschnitt wird beschrieben, wie Funktionen in LINQ to Entities-Abfragen aufgerufen werden.  
  
 Die <xref:System.Data.Objects.EntityFunctions>-Klasse und die <xref:System.Data.Objects.SqlClient.SqlFunctions>-Klasse bieten im Rahmen des Entity Framework Zugriff auf kanonische Funktionen und Datenbankfunktionen. Weitere Informationen finden Sie unter [Vorgehensweise: Kanonische Funktionen](how-to-call-canonical-functions.md) und [Gewusst wie: Ruft Daten Bank](how-to-call-database-functions.md)Funktionen auf.  
  
 Zum Aufrufen einer benutzerdefinierten Funktion sind drei grundlegende Schritte erforderlich:  
  
1. Definieren Sie im konzeptionellen Modell eine Funktion, oder deklarieren Sie im Speichermodell eine Funktion.  
  
2. Fügen Sie der Anwendung eine Methode hinzu, und ordnen Sie es mit einem <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute> der Funktion im Modell zu.  
  
3. Rufen Sie die Funktion in einer LINQ to Entities-Abfrage auf.  
  
 Weitere Informationen hierzu finden Sie in diesem Abschnitt.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Vorgehensweise: Kanonische Funktionen aufzurufen](how-to-call-canonical-functions.md)  
  
 [Vorgehensweise: Datenbankfunktionen aufzurufen](how-to-call-database-functions.md)  
  
 [Vorgehensweise: Benutzerdefinierte Datenbankfunktionen aufzurufen](how-to-call-custom-database-functions.md)  
  
 [Vorgehensweise: Modell definierte Funktionen in Abfragen abrufen](how-to-call-model-defined-functions-in-queries.md)  
  
 [Vorgehensweise: Aufgerufen Modell definierter Funktionen als Objektmethoden](how-to-call-model-defined-functions-as-object-methods.md)  
  
## <a name="see-also"></a>Siehe auch

- [Abfragen in LINQ to Entities](queries-in-linq-to-entities.md)
- [Canonical Functions (Kanonische Funktionen)](canonical-functions.md)
- [Übersicht über die EDMX-Datei](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc982042(v=vs.100))
- [Vorgehensweise: Definieren von benutzerdefinierten Funktionen im konzeptionellen Modell](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/dd456812(v=vs.100))
