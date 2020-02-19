---
title: Signieren von gespeicherten Prozeduren in SQL Server
ms.date: 01/05/2018
ms.assetid: eeed752c-0084-48e5-9dca-381353007a0d
ms.openlocfilehash: 0131655d06a6ef543ea460d04739401538cac04b
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452356"
---
# <a name="signing-stored-procedures-in-sql-server"></a>Signieren von gespeicherten Prozeduren in SQL Server

Bei einer digitalen Signatur handelt es sich um einen Datendigest, der mit dem privaten Schlüssel des Signaturgebers verschlüsselt wurde. Durch den privaten Schlüssel ist sichergestellt, dass die digitale Signatur eindeutig vom Träger oder Besitzer der Signatur stammt. Sie können gespeicherte Prozeduren, Funktionen (mit Ausnahme von Inline-Tabellenwert Funktionen), Trigger und Assemblys signieren.

Sie können gespeicherte Prozeduren mit einem Zertifikat oder einem asymmetrischen Schlüssel signieren. Gedacht ist dies für Szenarien, in denen Berechtigungen nicht über die Besitzverkettung geerbt werden können oder in denen die Besitzkette unterbrochen ist, wie bei dynamischem SQL. Anschließend können Sie einen Benutzer erstellen, der dem Zertifikat zugeordnet ist, und dem Zertifikat Benutzerberechtigungen für die Objekte erteilen, auf die die gespeicherte Prozedur zugreifen muss.

Sie können auch einen Anmelde Namen erstellen, der demselben Zertifikat zugeordnet ist, und dann allen erforderlichen Berechtigungen auf Serverebene für diesen Anmelde Namen erteilen oder den Anmelde Namen einer oder mehreren der Server Rollen hinzufügen. Dadurch wird vermieden, dass die `TRUSTWORTHY`-Datenbankeinstellung für Szenarios aktiviert werden soll, in denen Berechtigungen höherer Ebene erforderlich sind.

Beim Ausführen der gespeicherten Prozedur werden SQL Server die Berechtigungen des Zertifikats Benutzers und/oder die Anmeldung mit den Berechtigungen des Aufrufers kombiniert. Anders als bei der `EXECUTE AS`-Klausel wird der Ausführungs Kontext der Prozedur nicht geändert. Integrierte Funktionen, die Anmelde- und Benutzernamen zurückgeben, geben den Namen des Aufrufers, und nicht den Namen des Zertifikatsbenutzers zurück.

## <a name="creating-certificates"></a>Erstellen von Zertifikaten

Wenn Sie eine gespeicherte Prozedur mit einem Zertifikat oder einem asymmetrischen Schlüssel signieren, wird ein Daten Digest, der aus dem verschlüsselten Hash des Codes der gespeicherten Prozedur zusammen mit dem EXECUTE-AS-Benutzer besteht, mithilfe des privaten Schlüssels erstellt. Zur Laufzeit wird der Datenhashwert mit dem öffentlichen Schlüssel entschlüsselt und mit dem Hashwert der gespeicherten Prozedur verglichen. Wenn Sie den EXECUTE-AS-Benutzer ändern, wird der Hashwert ungültig, damit die digitale Signatur nicht mehr übereinstimmt. Wenn Sie die gespeicherte Prozedur ändern, wird die Signatur vollständig gelöscht, wodurch verhindert wird, dass jemand, der keinen Zugriff auf den privaten Schlüssel hat, den Code der gespeicherten Prozedur ändert. In beiden Fällen müssen Sie die Prozedur jedes Mal neu signieren, wenn Sie den Code oder den EXECUTE-AS-Benutzer ändern.

Zum Signieren eines Moduls müssen zwei Schritte ausgeführt werden:

1. Erstellen Sie mit der Transact-SQL-`CREATE CERTIFICATE [certificateName]`-Anweisung ein Zertifikat. Diese Anweisung verfügt über mehrere Optionen, mit denen das Start- und Enddatum und ein Kennwort festgelegt werden können. Das Standard Ablaufdatum beträgt ein Jahr.

1. Signieren Sie die Prozedur mit dem Zertifikat. Verwenden Sie dazu die Transact-SQL-`ADD SIGNATURE TO [procedureName] BY CERTIFICATE [certificateName]`-Anweisung.

Nachdem das Modul signiert wurde, muss mindestens ein Prinzipal erstellt werden, um die zusätzlichen Berechtigungen zu speichern, die dem Zertifikat zugeordnet werden sollen.

Wenn das Modul zusätzliche Berechtigungen auf Datenbankebene benötigt:

1. Erstellen Sie mit der Transact-SQL-`CREATE USER [userName] FROM CERTIFICATE [certificateName]`-Anweisung einen mit diesem Zertifikat verknüpften Datenbankbenutzer. Dieser Benutzer ist nur in der-Datenbank vorhanden und ist nicht mit einem-Anmelde Namen verknüpft, es sei denn, es wurde auch ein Anmelde Name aus demselben Zertifikat erstellt.

1. Erteilen Sie dem Zertifikat Benutzer die erforderlichen Berechtigungen auf Datenbankebene.

Wenn das Modul zusätzliche Berechtigungen auf Serverebene benötigt:

1. Kopieren Sie das Zertifikat in die `master` Datenbank.

1. Erstellen Sie mit der Transact-SQL-`CREATE LOGIN [userName] FROM CERTIFICATE [certificateName]`-Anweisung einen diesem Zertifikat zugeordneten Anmelde Namen.

1. Erteilen Sie dem Zertifikat Anmelde Namen die erforderlichen Berechtigungen auf Serverebene.

> [!NOTE]
> Ein Zertifikat kann keine Berechtigungen für Benutzer gewähren, die Berechtigungen hatten, die mit der DENY-Anweisung widerrufen wurden. DENY hat immer Vorrang gegenüber GRANT und verhindert, dass der Aufrufer Berechtigungen erben kann, die dem Zertifikatsbenutzer gewährt wurden.

## <a name="external-resources"></a>Externe Ressourcen

Weitere Informationen finden Sie in den folgenden Ressourcen.

|Ressource|Beschreibung|
|--------------|-----------------|
|[Modul Signierung](https://docs.microsoft.com/previous-versions/sql/sql-server-2008/ms345102(v=sql.100))|Beschreibt das Signieren von Modulen, das Bereitstellen eines Beispiel Szenarios und Links zu den relevanten Transact-SQL-Artikeln.|
|[Signieren von gespeicherten Prozeduren mit einem Zertifikat](/sql/relational-databases/tutorial-signing-stored-procedures-with-a-certificate)|Enthält ein Lernprogramm zum Signieren einer gespeicherten Prozedur mit einem Zertifikat.|

## <a name="see-also"></a>Siehe auch

- [Sichern von ADO.NET-Anwendungen](../securing-ado-net-applications.md)
- [Übersicht über die SQL Server-Sicherheit](overview-of-sql-server-security.md)
- [Anwendungssicherheitsszenarios in SQL Server](application-security-scenarios-in-sql-server.md)
- [Verwalten von Berechtigungen mit gespeicherten Prozeduren in SQL Server](managing-permissions-with-stored-procedures-in-sql-server.md)
- [Schreiben von sicherem dynamischem SQL in SQL Server](writing-secure-dynamic-sql-in-sql-server.md)
- [Anpassen von Berechtigungen durch Identitätswechsel in SQL Server](customizing-permissions-with-impersonation-in-sql-server.md)
- [Ändern von Daten mit gespeicherten Prozeduren](../modifying-data-with-stored-procedures.md)
- [Übersicht über ADO.NET](../ado-net-overview.md)
