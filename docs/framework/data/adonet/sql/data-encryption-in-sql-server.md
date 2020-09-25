---
title: Datenverschlüsselung in SQL Server
ms.date: 03/30/2017
ms.assetid: 83b992f7-b351-4678-b4b9-f4ffd58134cc
ms.openlocfilehash: d0bda11f1a2933d096aa91d2be79d3af35172284
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91169530"
---
# <a name="data-encryption-in-sql-server"></a>Datenverschlüsselung in SQL Server

Mit den SQL Server-Funktionen können Sie Daten mithilfe eines Zertifikats, eines asymmetrischen Schlüssels oder eines symmetrischen Schlüssels verschlüsseln und entschlüsseln. Die Verwaltung der Zertifikate bzw. Schlüssel erfolgt in einem internen Zertifikatspeicher. Der Speicher verwendet eine Verschlüsselungshierarchie, die Zertifikate und Schlüssel auf einer Ebene zusammen mit der nächsthöheren Ebene in der Hierarchie sichert. Dieser Funktionsbereich von SQL Server wird als "Speicherung geheimer Schlüssel" bezeichnet.  
  
 Unter den von den Verschlüsselungsfunktionen unterstützten Verschlüsselungen ist das Verschlüsseln mit einem symmetrischen Schlüssel die schnellste Verschlüsselungsmethode. Diese Form der Verschlüsselung bietet sich an, wenn große Datenmengen verschlüsselt werden müssen. Die symmetrischen Schlüssel können durch Zertifikate, Kennwörter oder andere symmetrische Schlüssel verschlüsselt werden.  
  
## <a name="keys-and-algorithms"></a>Schlüssel und Algorithmen  

 SQL Server unterstützt verschiedene Verschlüsselungsalgorithmen mit symmetrischen Schlüsseln, darunter DES, Triple DES, RC2, RC4, 128-Bit RC4, DESX, 128-Bit AES, 192-Bit AES und 256-Bit AES. Die Algorithmen werden mit der Windows Krypto-API implementiert.  
  
 Innerhalb des Bereichs einer Datenbankverbindung kann SQL Server mehrere geöffnete symmetrische Schlüssel verwalten. Ein geöffneter Schlüssel wird vom Speicher abgerufen und steht zum Entschlüsseln von Daten zur Verfügung. Zum Entschlüsseln von Daten muss der zu verwendende symmetrische Schlüssel nicht angegeben werden. Jeder verschlüsselte Wert enthält die Schlüssel-ID (Haupt-GUID) des Schlüssels, mit dem er verschlüsselt wurde. Die Engine ordnet den verschlüsselten Datenstream einem geöffneten symmetrischen Schlüssel zu, wenn der richtige Schlüssel entschlüsselt wurde und geöffnet ist. Dieser Schlüssel wird dann zur Entschlüsselung und zur Rückgabe der Daten verwendet. Wenn der richtige Schlüssel nicht geöffnet ist, wird NULL zurückgegeben.  
  
 Ein Beispiel für das Arbeiten mit verschlüsselten Daten in einer-Datenbank finden Sie unter [Verschlüsseln einer Datenspalte](/sql/relational-databases/security/encryption/encrypt-a-column-of-data).
  
## <a name="external-resources"></a>Externe Ressourcen  

 Weitere Informationen zur Datenverschlüsselung finden Sie in den folgenden Ressourcen:  
  
|Resource|Beschreibung|  
|-|-|  
|[SQL Server-Verschlüsselung](/sql/relational-databases/security/encryption/sql-server-encryption)|Bietet eine Übersicht über die Verschlüsselung in SQL Server. Dieses Thema enthält Links zu weiteren Artikeln.|  
|[Verschlüsselungshierarchie](/sql/relational-databases/security/encryption/encryption-hierarchy)|Bietet eine Übersicht über die Verschlüsselung in SQL Server. Dieses Thema enthält Links zu weiteren Artikeln.|  
  
## <a name="see-also"></a>Weitere Informationen

- [Sichern von ADO.NET-Anwendungen](../securing-ado-net-applications.md)
- [Anwendungssicherheitsszenarios in SQL Server](application-security-scenarios-in-sql-server.md)
- [Authentifizierung in SQL Server](authentication-in-sql-server.md)
- [Server- und Datenbankrollen in SQL Server](server-and-database-roles-in-sql-server.md)
- [Objektbesitz und Trennung von Benutzer und Schema in SQL Server](ownership-and-user-schema-separation-in-sql-server.md)
- [Autorisierung und Berechtigungen in SQL Server](authorization-and-permissions-in-sql-server.md)
- [Übersicht über ADO.NET](../ado-net-overview.md)
