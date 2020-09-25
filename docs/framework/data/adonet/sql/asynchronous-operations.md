---
title: Asynchrone Vorgänge
ms.date: 03/30/2017
ms.assetid: e7d32c3c-bf78-4bfc-a357-c9e82e4a4b3c
ms.openlocfilehash: f94a33b1ff06b5433f61687b8e28096ea37b412a
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91197585"
---
# <a name="asynchronous-operations"></a>Asynchrone Vorgänge

Einige Datenbankvorgänge, z. B. Befehlsausführungen, können beträchtliche Zeit in Anspruch nehmen. In derartigen Fällen müssen Singlethread-Anwendungen andere Vorgänge blockieren und warten, bis der Befehl abgeschlossen ist, ehe ihre eigenen Vorgänge fortgesetzt werden können. Im Gegensatz dazu kann der Vordergrundthread während des gesamten Vorgangs aktiv bleiben, wenn der Vorgang mit langer Ausführungszeit einem Hintergrundthread zugewiesen werden kann. In einer Windows-Anwendung beispielsweise ermöglicht das Delegieren des Vorgangs mit langer Ausführungszeit an einen Hintergrundthread, dass der Benutzeroberflächenthread während der Ausführung des Vorgangs reaktionsfähig bleibt.  
  
 .NET Framework stellt mehrere asynchrone Standardentwurfsmuster bereit, mit denen Entwickler die Vorteile der Hintergrundthreads nutzen können und die dem Benutzeroberflächenthread oder Threads mit hoher Priorität die Möglichkeit geben, andere Operationen zu beenden. ADO.NET unterstützt dieselben Entwurfsmuster in seiner <xref:System.Data.SqlClient.SqlCommand>-Klasse. Insbesondere die Methoden <xref:System.Data.SqlClient.SqlCommand.BeginExecuteNonQuery%2A>, <xref:System.Data.SqlClient.SqlCommand.BeginExecuteReader%2A> und <xref:System.Data.SqlClient.SqlCommand.BeginExecuteXmlReader%2A> gepaart mit den Methoden <xref:System.Data.SqlClient.SqlCommand.EndExecuteNonQuery%2A>, <xref:System.Data.SqlClient.SqlCommand.EndExecuteReader%2A> und <xref:System.Data.SqlClient.SqlCommand.EndExecuteXmlReader%2A> bieten die asynchrone Unterstützung.  
  
> [!NOTE]
> Asynchrone Programmierung ist eine grundlegende Funktion von .NET Framework, und ADO.NET nutzt die Möglichkeiten der Standardentwurfsmuster vollständig. Weitere Informationen zu den verschiedenen asynchronen Techniken, die Entwicklern zur Verfügung stehen, finden Sie unter [Asynchrones Aufrufen von synchronen Methoden](../../../../standard/asynchronous-programming-patterns/calling-synchronous-methods-asynchronously.md).  
  
 Auch wenn durch die Verwendung asynchroner Techniken mit ADO.NET-Funktionen keine neuen Aspekte hinzugefügt werden, ist es wahrscheinlicher, dass Entwickler asynchrone Funktionen in ADO.NET verwenden als in anderen Bereichen von .NET Framework. Es ist wichtig, mit den Vorteilen und potenziellen Fehlerquellen beim Erstellen von Multithread-Anwendungen vertraut zu sein. Die folgenden Beispiele in diesem Abschnitt weisen auf mehrere wichtige Punkte hin, die Entwickler bei der Erstellung von Anwendungen mit Multithread-Funktionalität berücksichtigen müssen.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  

 [Windows-Anwendungen, die Rückrufe verwenden](windows-applications-using-callbacks.md)  
 Bietet ein Beispiel, das zeigt, wie ein asynchroner Befehl sicher ausgeführt werden kann, wobei die Interaktion mit einem Formular und dessen Inhalt in einem separaten Thread ordnungsgemäß gehandhabt wird.  
  
 [ASP.NET-Anwendungen mit Wait-Handles](aspnet-apps-using-wait-handles.md)  
 Enthält ein Beispiel, das veranschaulicht, wie mehrere gleichzeitige Befehle auf einer ASP.NET-Seite ausgeführt werden können, wobei Wait-Handles verwendet werden, um den Vorgang nach Ausführung aller Befehle zu verwalten.  
  
 [Abrufen in Konsolen Anwendungen](polling-in-console-applications.md)  
 Enthält ein Beispiel, das die Verwendung von Abrufen demonstriert, um in einer Konsolenanwendung auf den Abschluss der Ausführung eines asynchronen Befehls zu warten. Diese Technik eignet sich auch in einer Klassenbibliothek oder einer anderen Anwendung ohne Benutzerschnittstelle.  
  
## <a name="see-also"></a>Weitere Informationen

- [SQL Server und ADO.NET](index.md)
- [Asynchrones Aufrufen von synchronen Methoden](../../../../standard/asynchronous-programming-patterns/calling-synchronous-methods-asynchronously.md)
- [Übersicht über ADO.NET](../ado-net-overview.md)
