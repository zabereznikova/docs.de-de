---
title: Datenverschlüsselung in SQL Server
ms.date: 03/30/2017
ms.assetid: 83b992f7-b351-4678-b4b9-f4ffd58134cc
ms.openlocfilehash: 9e2924dc9f2f2954f6690ad5009c4143d1b9a44f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33358367"
---
# <a name="data-encryption-in-sql-server"></a>Datenverschlüsselung in SQL Server
Mit den SQL Server-Funktionen können Sie Daten mithilfe eines Zertifikats, eines asymmetrischen Schlüssels oder eines symmetrischen Schlüssels verschlüsseln und entschlüsseln. Die Verwaltung der Zertifikate bzw. Schlüssel erfolgt in einem internen Zertifikatspeicher. Der Speicher verwendet eine Verschlüsselungshierarchie, die Zertifikate und Schlüssel auf einer Ebene zusammen mit der nächsthöheren Ebene in der Hierarchie sichert. Dieser Funktionsbereich von SQL Server wird als "Speicherung geheimer Schlüssel" bezeichnet.  
  
 Unter den von den Verschlüsselungsfunktionen unterstützten Verschlüsselungen ist das Verschlüsseln mit einem symmetrischen Schlüssel die schnellste Verschlüsselungsmethode. Diese Form der Verschlüsselung bietet sich an, wenn große Datenmengen verschlüsselt werden müssen. Die symmetrischen Schlüssel können durch Zertifikate, Kennwörter oder andere symmetrische Schlüssel verschlüsselt werden.  
  
## <a name="keys-and-algorithms"></a>Schlüssel und Algorithmen  
 SQL Server unterstützt verschiedene Verschlüsselungsalgorithmen mit symmetrischen Schlüsseln, darunter DES, Triple DES, RC2, RC4, 128-Bit RC4, DESX, 128-Bit AES, 192-Bit AES und 256-Bit AES. Die Algorithmen werden mit der Windows Krypto-API implementiert.  
  
 Innerhalb des Bereichs einer Datenbankverbindung kann SQL Server mehrere geöffnete symmetrische Schlüssel verwalten. Ein geöffneter Schlüssel wird vom Speicher abgerufen und steht zum Entschlüsseln von Daten zur Verfügung. Zum Entschlüsseln von Daten muss der zu verwendende symmetrische Schlüssel nicht angegeben werden. Jeder verschlüsselte Wert enthält die Schlüssel-ID (Haupt-GUID) des Schlüssels, mit dem er verschlüsselt wurde. Das Modul ordnet den verschlüsselten Datenstream einem geöffneten symmetrischen Schlüssel zu, wenn der richtige Schlüssel entschlüsselt wurde und geöffnet ist. Dieser Schlüssel wird dann zur Entschlüsselung und zur Rückgabe der Daten verwendet. Wenn der richtige Schlüssel nicht geöffnet ist, wird NULL zurückgegeben.  
  
 Ein Beispiel, das veranschaulicht, wie mit verschlüsselten Daten in einer Datenbank arbeiten, finden Sie unter [wie: Verschlüsseln einer Datenspalte](http://go.microsoft.com/fwlink/?LinkID=128559) in SQL Server-Onlinedokumentation.  
  
## <a name="external-resources"></a>Externe Ressourcen  
 Weitere Informationen zur Datenverschlüsselung finden Sie in den folgenden Ressourcen:  
  
|||  
|-|-|  
|[SQL Server-Verschlüsselung](http://msdn.microsoft.com/library/bb510663.aspx) in SQL Server-Onlinedokumentation|Bietet eine Übersicht über die Verschlüsselung in SQL Server. Dieses Thema enthält außerdem Links zu weiterführenden und Gewusst-wie-Themen.|  
|[Verschlüsselungshierarchie](http://msdn.microsoft.com/library/ms189586.aspx) und [Verschlüsselung: Themen zur Vorgehensweise](http://msdn.microsoft.com/library/aa337557.aspx) in SQL Server-Onlinedokumentation|Bietet eine Übersicht über die Verschlüsselung in SQL Server. Dieses Thema enthält Links zu weiterführenden und Gewusst-wie-Themen.|  
  
## <a name="see-also"></a>Siehe auch  
 [Sichern von ADO.NET-Anwendungen](../../../../../docs/framework/data/adonet/securing-ado-net-applications.md)  
 [Anwendungssicherheitsszenarios in SQL Server](../../../../../docs/framework/data/adonet/sql/application-security-scenarios-in-sql-server.md)  
 [Authentifizierung in SQL Server](../../../../../docs/framework/data/adonet/sql/authentication-in-sql-server.md)  
 [Server- und Datenbankrollen in SQL Server](../../../../../docs/framework/data/adonet/sql/server-and-database-roles-in-sql-server.md)  
 [Objektbesitz und Trennung von Benutzer und Schema in SQL Server](../../../../../docs/framework/data/adonet/sql/ownership-and-user-schema-separation-in-sql-server.md)  
 [Autorisierung und Berechtigungen in SQL Server](../../../../../docs/framework/data/adonet/sql/authorization-and-permissions-in-sql-server.md)  
 [ADO.NET Managed Provider und DataSet Developer Center](http://go.microsoft.com/fwlink/?LinkId=217917)
