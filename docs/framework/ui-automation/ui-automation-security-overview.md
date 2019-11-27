---
title: Übersicht über die Benutzeroberflächenautomatisierungs-Sicherheit
ms.date: 03/30/2017
helpviewer_keywords:
- UI Automation, security model
- security model, UI Automation
ms.assetid: 1d853695-973c-48ae-b382-4132ae702805
ms.openlocfilehash: 70d24c3dcc531abcec6d4dce75b5f0b31757e0c0
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448771"
---
# <a name="ui-automation-security-overview"></a>Übersicht über die Benutzeroberflächenautomatisierungs-Sicherheit

> [!NOTE]
> Diese Dokumentation ist für .NET Framework-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Klassen verwenden möchten, die im <xref:System.Windows.Automation>-Namespace definiert sind. Aktuelle Informationen zur [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]finden Sie auf der Seite zur [Windows-Automatisierungs-API: UI-Automatisierung](/windows/win32/winauto/entry-uiauto-win32).

In dieser Übersicht wird das Sicherheitsmodell für [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] in Windows Vista beschrieben.

<a name="User_Account_Control"></a>

## <a name="user-account-control"></a>Benutzerkontensteuerung

Sicherheit ist ein wichtiger Schwerpunkt von Windows Vista. zu den Neuerungen zählt die Möglichkeit für Benutzer, als Standardbenutzer (nicht Administrator) auszuführen, ohne dass die Ausführung von Anwendungen und Diensten, die höhere Berechtigungen erfordern, nicht unbedingt blockiert ist.

In Windows Vista werden die meisten Anwendungen entweder mit einem Standard-oder einem Administrator Token bereitgestellt. Wenn eine Anwendung nicht als Administratoranwendung identifiziert werden kann, wird sie standardmäßig als Standardanwendung gestartet. Bevor eine Anwendung, die als administrative Anwendung identifiziert wird, gestartet werden kann, fordert Windows Vista den Benutzer zur Zustimmung auf, die Anwendung mit erhöhten Rechten auszuführen. Die Aufforderung zur Zustimmung wird standardmäßig angezeigt, auch wenn der Benutzer ein Mitglied der lokalen Administratorgruppe ist, da auch Administratoren mit den Rechten von Standardbenutzern agieren, bis eine Anwendung oder Systemkomponente, für die Administratorberechtigungen erforderlich sind, die Ausführungserlaubnis anfordert.

<a name="Tasks_Requiring_Higher_Privileges"></a>

## <a name="tasks-requiring-higher-privileges"></a>Aufgaben, für die erhöhte Rechte erforderlich sind

Wenn ein Benutzer versucht, eine Aufgabe auszuführen, für die Administrator Berechtigungen erforderlich sind, zeigt Windows Vista ein Dialogfeld an, in dem der Benutzer zum Fortfahren aufgefordert wird. Dieses Dialogfeld ist gegen prozessübergreifenden Datenaustausch geschützt, sodass Schadsoftware keine Benutzereingaben simulieren kann. Analog dazu kann auch auf den Anmeldebildschirm auf dem Desktop nicht durch andere Prozesse zugegriffen werden.

Benutzeroberflächenautomatisierungs-Clients müssen mit anderen Prozessen kommunizieren, von denen einige möglicherweise mit erhöhten Rechten ausgeführt werden. Darüber hinaus benötigen Clients möglicherweise Zugriff auf die Systemdialogfelder, die für andere Prozesse normalerweise nicht sichtbar sind. Daher müssen [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Clients aus Sicht des Systems als vertrauenswürdig eingestuft sein und mit besonderen Berechtigungen ausgeführt werden.

Damit sie für den Datenaustausch mit Anwendungen, die mit höheren Berechtigungsstufen ausgeführt werden, als vertrauenswürdig angesehen werden, müssen Anwendungen signiert sein.

<a name="Manifest_Files"></a>

## <a name="manifest-files"></a>Manifestdateien

Für den Zugriff auf die Benutzeroberfläche des geschützten Systems müssen Anwendungen wie folgt mit einer Manifest-Datei erstellt werden, die das `uiAccess`-Attribut im `requestedExecutionLevel`-Tag enthält:

```xml
<trustInfo xmlns="urn:schemas-microsoft-com:asm.v3">
  <security>
    <requestedPrivileges>
      <requestedExecutionLevel
        level="highestAvailable"
        uiAccess="true" />
    </requestedPrivileges>
  </security>
</trustInfo>
```

Der Wert des `level` -Attributs in diesem Code stellt nur ein Beispiel dar.

`uiAccess` ist standardmäßig "false". Das heißt, wenn das Attribut ausgelassen wird oder kein Manifest für die Assembly vorhanden ist, kann die Anwendung keinen Zugriff auf die geschützte Benutzeroberfläche erhalten.
