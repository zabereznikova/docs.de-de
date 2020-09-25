---
title: Erstellen von Anwendungsrollen in SQL Server
ms.date: 03/30/2017
ms.assetid: 27442435-dfb2-4062-8c59-e2960833a638
ms.openlocfilehash: 764ae61cba4bf01681d658cc4aacc2aeaecedd3f
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91173548"
---
# <a name="creating-application-roles-in-sql-server"></a>Erstellen von Anwendungsrollen in SQL Server

Anwendungsrollen bieten die Möglichkeit, einer Anwendung anstelle von Datenbankrollen oder Benutzern Berechtigungen zuzuweisen. Benutzer können eine Verbindung mit der Datenbank herstellen, die Anwendungsrolle aktivieren und die der Anwendung erteilten Berechtigungen annehmen. Die der Anwendungsrolle gewährten Berechtigungen sind so lange in Kraft, wie die Verbindung besteht.  
  
> [!IMPORTANT]
> Anwendungsrollen werden aktiviert, wenn eine Clientanwendung in der Verbindungszeichenfolge einen Anwendungsrollennamen und ein Kennwort bereitstellt. In 2-Ebenen-Anwendungen stellen Anwendungsrollen ein Sicherheitsrisiko dar, weil das Kennwort auf dem Clientcomputer gespeichert werden muss. In 3-Ebenen-Anwendungen können Sie das Kennwort so speichern, dass die Benutzer der Anwendung nicht darauf zugreifen können.  
  
## <a name="application-role-features"></a>Funktionen der Anwendungsrollen  

 Anwendungsrollen weisen die folgenden Funktionen auf:  
  
- Im Unterschied zu Datenbankrollen enthalten Anwendungsrollen keine Member.  
  
- Anwendungsrollen werden aktiviert, wenn eine Anwendung der gespeicherten Systemprozedur `sp_setapprole` einen Anwendungsrollennamen und ein Kennwort bereitstellt.  
  
- Das Kennwort muss auf dem Clientcomputer gespeichert und zur Laufzeit bereitgestellt werden. Die Aktivierung der Anwendungsrolle von SQL Server aus ist nicht möglich.  
  
- Das Kennwort wird nicht verschlüsselt. Das Parameterkennwort wird als unidirektionaler Hash gespeichert.  
  
- Einmal aktiviert, bleiben durch die Anwendungsrolle abgerufene Berechtigungen für die gesamte Dauer der Verbindung wirksam.  
  
- Die Anwendungsrolle erbt die der Rolle `public` gewährten Berechtigungen.  
  
- Wenn ein Member der festen Serverrolle `sysadmin` eine Anwendungsrolle aktiviert, wechselt der Sicherheitskontext für die Dauer der Verbindung zum Sicherheitskontext der Anwendungsrolle.  
  
- Wenn Sie in einer Datenbank ein `guest`-Konto erstellen, das eine Anwendungsrolle besitzt, müssen Sie kein Datenbankbenutzerkonto für die Anwendungsrolle oder für eine der Anmeldungen erstellen, die die Rolle aufrufen. Anwendungsrollen können auf eine andere Datenbank nur direkt zugreifen, wenn in dieser anderen Datenbank ein `guest`-Konto vorhanden ist.  
  
- Integrierte Funktionen, die Anmeldenamen, z. B. SYSTEM_USER, zurückgeben, geben den Namen der Anmeldung zurück, die die Anwendungsrolle aufgerufen hat. Integrierte Funktionen, die Datenbankbenutzernamen zurückgeben, geben den Namen der Anwendungsrolle zurück.  
  
### <a name="the-principle-of-least-privilege"></a>Das Prinzip der minimalen Rechtegewährung  

 Anwendungsrollen sollten immer nur die unbedingt notwendigen Berechtigungen gewährt werden, um so für den Fall vorzusorgen, dass das Kennwort in die falschen Hände gerät. Berechtigungen für die Rolle `public` sollten in allen Datenbanken, die eine Anwendungsrolle verwenden, widerrufen werden. Deaktivieren Sie das `guest`-Konto in allen Datenbanken, auf die Inhaber der Anwendungsrolle keinen Zugriff haben sollen.  
  
### <a name="application-role-enhancements"></a>Verbesserungen bei den Anwendungsrollen  

 Der Ausführungskontext kann wieder zum ursprünglichen Aufrufer zurückwechseln, nachdem eine Anwendungsrolle aktiviert wurde, sodass das Verbindungspooling nicht deaktiviert werden muss. Die `sp_setapprole`-Prozedur verfügt über eine neue Option, die ein Cookie erstellt, das Kontextinformationen zum Aufrufer enthält. Sie können die Sitzung wiederherstellen, indem Sie die `sp_unsetapprole`-Prozedur aufrufen und ihr das Cookie übergeben.  
  
## <a name="application-role-alternatives"></a>Alternativen zu Anwendungsrollen  

 Anwendungsrollen sind von der Sicherheit eines Kennworts abhängig und stellen so ein potenzielles Sicherheitsrisiko dar. Kennwörter, die in den Anwendungscode eingebettet sind oder auf der Festplatte gespeichert werden, können leicht ausspioniert werden.  
  
 Sie sollten die folgenden Alternativen in Erwägung ziehen.  
  
- Verwenden Sie Kontextwechsel mit der EXECUTE AS-Anweisung und deren Klauseln NO REVERT und WITH COOKIE. Sie können ein Benutzerkonto in einer Datenbank erstellen, das keiner Anmeldung zugeordnet ist. Anschließend weisen Sie diesem Konto Berechtigungen zu. Die Verwendung von EXECUTE AS mit einem login-less-Benutzer ist sicherer, da sie auf Berechtigungen und nicht auf dem Kennwort basiert. Weitere Informationen finden Sie unter [Anpassen von Berechtigungen mit Identitätswechsel in SQL Server](customizing-permissions-with-impersonation-in-sql-server.md).  
  
- Signieren Sie gespeicherte Prozeduren mit Zertifikaten, die nur die Berechtigung gewähren, die zum Ausführen der Prozeduren notwendig ist. Weitere Informationen finden Sie [unter Signieren von gespeicherten Prozeduren in SQL Server](signing-stored-procedures-in-sql-server.md).  
  
## <a name="external-resources"></a>Externe Ressourcen  

 Weitere Informationen finden Sie in den folgenden Ressourcen.  
  
|Resource|Beschreibung|  
|--------------|-----------------|  
|[Anwendungsrollen](/sql/relational-databases/security/authentication-access/application-roles)|Beschreibt das Erstellen und Verwenden von Anwendungsrollen in SQL Server 2008.|  
  
## <a name="see-also"></a>Weitere Informationen

- [Sichern von ADO.NET-Anwendungen](../securing-ado-net-applications.md)
- [Übersicht über die SQL Server-Sicherheit](overview-of-sql-server-security.md)
- [Anwendungssicherheitsszenarios in SQL Server](application-security-scenarios-in-sql-server.md)
- [Übersicht über ADO.NET](../ado-net-overview.md)
