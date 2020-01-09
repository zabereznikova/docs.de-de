---
title: Übersicht über das Factorymodell
ms.date: 03/30/2017
ms.assetid: b5dc81c4-7554-44b9-b513-769bd61e2e7b
ms.openlocfilehash: f344502453acbbb5c08e49b7c21a0f4e84a29ffa
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/25/2019
ms.locfileid: "75348397"
---
# <a name="factory-model-overview"></a>Übersicht über das Factorymodell
In ADO.NET 2.0 wurden im <xref:System.Data.Common>-Namespace neue Basisklassen eingeführt. Die Basisklassen sind abstrakt, können also nicht direkt instanziiert werden. Zu ihnen gehören die Basisklassen <xref:System.Data.Common.DbConnection>, <xref:System.Data.Common.DbCommand> und <xref:System.Data.Common.DbDataAdapter>. Sie werden von den .NET Framework-Datenanbietern, z. B. <xref:System.Data.SqlClient> und <xref:System.Data.OleDb>, gemeinsam genutzt. Die neuen Basisklassen vereinfachen das Hinzufügen neuer Funktionen zu den .NET Framework-Datenanbietern, ohne dass dazu neue Schnittstellen erstellt werden müssen.  
  
 Außerdem wurden abstrakte Basisklassen in ADO.NET 2.0 eingeführt, mit denen Entwickler in der Lage sind, generischen Datenzugriffscode zu schreiben, der datenanbieterunabhängig ist.  
  
## <a name="the-factory-design-pattern"></a>Das Factoryentwurfsmuster  
 Das Programmiermodell zum Schreiben anbieterunabhängigen Codes basiert auf der Verwendung des Factoryentwurfsmusters, das für den Zugriff auf Datenbanken mehrerer Anbieter eine einzige API vewendet. Dieses Muster ist geeignet benannt, da es die Verwendung eines spezialisierten Objekts nur zum Erstellen anderer Objekte bedingt, wie in einer realen Produktionsumgebung. Eine ausführlichere Beschreibung des Factoryentwurfsmusters finden Sie unter [Schreiben von generischem Datenzugriffs Code in ASP.NET 2,0 und ADO.NET 2,0](https://docs.microsoft.com/previous-versions/dotnet/articles/ms971499(v=msdn.10)).
  
 Ab ADO.NET 2.0 stellt die <xref:System.Data.Common.DbProviderFactories>-Klasse zum Erstellen einer `static`-Instanz `Shared`-Methoden (in Visual Basic <xref:System.Data.Common.DbProviderFactory>-Methoden) bereit. Die Instanz gibt dann anhand der Anbieterinformationen und der zur Laufzeit bereitgestellten Verbindungszeichenfolge ein korrektes, stark typisiertes Objekt zurück.  
  
## <a name="see-also"></a>Siehe auch

- [Abrufen einer DbProviderFactory](obtaining-a-dbproviderfactory.md)
- [DbConnection, DbCommand und DbException](dbconnection-dbcommand-and-dbexception.md)
- [Ändern von Daten mit DbDataAdapter](modifying-data-with-a-dbdataadapter.md)
- [Übersicht über ADO.NET](ado-net-overview.md)
