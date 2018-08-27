---
title: Datenverschlüsselung in SQL Server
ms.date: 03/30/2017
ms.assetid: 83b992f7-b351-4678-b4b9-f4ffd58134cc
ms.openlocfilehash: d662f04cb54e12abfc481487cb5172f63edf0316
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2018
ms.locfileid: "42932743"
---
# <a name="data-encryption-in-sql-server"></a>Datenverschlüsselung in SQL Server
Mit den SQL Server-Funktionen können Sie Daten mithilfe eines Zertifikats, eines asymmetrischen Schlüssels oder eines symmetrischen Schlüssels verschlüsseln und entschlüsseln. Die Verwaltung der Zertifikate bzw. Schlüssel erfolgt in einem internen Zertifikatspeicher. Der Speicher verwendet eine Verschlüsselungshierarchie, die Zertifikate und Schlüssel auf einer Ebene zusammen mit der nächsthöheren Ebene in der Hierarchie sichert. Dieser Funktionsbereich von SQL Server wird als "Speicherung geheimer Schlüssel" bezeichnet.  
  
 Unter den von den Verschlüsselungsfunktionen unterstützten Verschlüsselungen ist das Verschlüsseln mit einem symmetrischen Schlüssel die schnellste Verschlüsselungsmethode. Diese Form der Verschlüsselung bietet sich an, wenn große Datenmengen verschlüsselt werden müssen. Die symmetrischen Schlüssel können durch Zertifikate, Kennwörter oder andere symmetrische Schlüssel verschlüsselt werden.  
  
## <a name="keys-and-algorithms"></a>Schlüssel und Algorithmen  
 SQL Server unterstützt verschiedene Verschlüsselungsalgorithmen mit symmetrischen Schlüsseln, darunter DES, Triple DES, RC2, RC4, 128-Bit RC4, DESX, 128-Bit AES, 192-Bit AES und 256-Bit AES. Die Algorithmen werden mit der Windows Krypto-API implementiert.  
  
 Innerhalb des Bereichs einer Datenbankverbindung kann SQL Server mehrere geöffnete symmetrische Schlüssel verwalten. Ein geöffneter Schlüssel wird vom Speicher abgerufen und steht zum Entschlüsseln von Daten zur Verfügung. Zum Entschlüsseln von Daten muss der zu verwendende symmetrische Schlüssel nicht angegeben werden. Jeder verschlüsselte Wert enthält die Schlüssel-ID (Haupt-GUID) des Schlüssels, mit dem er verschlüsselt wurde. Das Modul ordnet den verschlüsselten Datenstream einem geöffneten symmetrischen Schlüssel zu, wenn der richtige Schlüssel entschlüsselt wurde und geöffnet ist. Dieser Schlüssel wird dann zur Entschlüsselung und zur Rückgabe der Daten verwendet. Wenn der richtige Schlüssel nicht geöffnet ist, wird NULL zurückgegeben.  
  
 Ein Beispiel, wie Sie in einer Datenbank mit verschlüsselten Daten arbeiten, finden Sie unter [Verschlüsseln einer Datenspalte](/sql/relational-databases/security/encryption/encrypt-a-column-of-data).
  
## <a name="external-resources"></a>Externe Ressourcen  
 Weitere Informationen zur Datenverschlüsselung finden Sie in den folgenden Ressourcen:  
  
|Ressource|Beschreibung|  
|-|-|  
|[SQL Server-Verschlüsselung](/sql/relational-databases/security/encryption/sql-server-encryption)|Bietet eine Übersicht über die Verschlüsselung in SQL Server. Dieses Thema enthält Links zu weiteren Artikeln.|  
|[Verschlüsselungshierarchie](/sql/relational-databases/security/encryption/encryption-hierarchy)|Bietet eine Übersicht über die Verschlüsselung in SQL Server. Dieses Thema enthält Links zu weiteren Artikeln.|  
  
## <a name="see-also"></a>Siehe auch  
 [Sichern von ADO.NET-Anwendungen](../../../../../docs/framework/data/adonet/securing-ado-net-applications.md)  
 [Anwendungssicherheitsszenarios in SQL Server](../../../../../docs/framework/data/adonet/sql/application-security-scenarios-in-sql-server.md)  
 [Authentifizierung in SQL Server](../../../../../docs/framework/data/adonet/sql/authentication-in-sql-server.md)  
 [Server- und Datenbankrollen in SQL Server](../../../../../docs/framework/data/adonet/sql/server-and-database-roles-in-sql-server.md)  
 [Objektbesitz und Trennung von Benutzer und Schema in SQL Server](../../../../../docs/framework/data/adonet/sql/ownership-and-user-schema-separation-in-sql-server.md)  
 [Autorisierung und Berechtigungen in SQL Server](../../../../../docs/framework/data/adonet/sql/authorization-and-permissions-in-sql-server.md)  
 [ADO.NET Managed Provider und DataSet Developer Center](http://go.microsoft.com/fwlink/?LinkId=217917)
