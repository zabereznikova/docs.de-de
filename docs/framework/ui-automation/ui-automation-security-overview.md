---
title: Übersicht über die Benutzeroberflächenautomatisierungs-Sicherheit
ms.date: 03/30/2017
helpviewer_keywords:
- UI Automation, security model
- security model, UI Automation
ms.assetid: 1d853695-973c-48ae-b382-4132ae702805
ms.openlocfilehash: 8b798aef528cccdedb1fcaa53c1782632037600d
ms.sourcegitcommit: 77e33b682db39955e331b8e8eda4ef1925a24e78
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/29/2019
ms.locfileid: "70133785"
---
# <a name="ui-automation-security-overview"></a>Übersicht über die Benutzeroberflächenautomatisierungs-Sicherheit

> [!NOTE]
> Diese Dokumentation ist für .NET Framework-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Klassen verwenden möchten, die im <xref:System.Windows.Automation>-Namespace definiert sind. Die neuesten Informationen zu [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]finden [Sie unter Windows Automation-API: Automatisierung](https://go.microsoft.com/fwlink/?LinkID=156746)der Benutzeroberfläche.

In dieser Übersicht wird das Sicherheitsmodell für [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] in [!INCLUDE[TLA#tla_winvista](../../../includes/tlasharptla-winvista-md.md)]beschrieben.

<a name="User_Account_Control"></a>

## <a name="user-account-control"></a>Benutzerkontensteuerung

Sicherheit stellt einen zentralen Schwerpunkt von [!INCLUDE[TLA#tla_winvista](../../../includes/tlasharptla-winvista-md.md)] dar, und zu den Neuerungen zählt die Möglichkeit für Benutzer, mit einer Anmeldung als Standardbenutzer (ohne Administratorberechtigungen) zu arbeiten, ohne grundsätzlich von der Ausführung von Anwendungen und Diensten ausgeschlossen zu sein, für die erhöhte Rechte erforderlich sind.

In [!INCLUDE[TLA2#tla_winvista](../../../includes/tla2sharptla-winvista-md.md)]werden die meisten Anwendungen entweder mit einem Standard- oder einem Administratortoken bereitgestellt. Wenn eine Anwendung nicht als Administratoranwendung identifiziert werden kann, wird sie standardmäßig als Standardanwendung gestartet. Vor dem Starten einer Anwendung, die als Administratoranwendung identifiziert wurde, bittet [!INCLUDE[TLA2#tla_winvista](../../../includes/tla2sharptla-winvista-md.md)] den Benutzer um seine Zustimmung zur Ausführung der Anwendung mit erhöhten Rechten. Die Aufforderung zur Zustimmung wird standardmäßig angezeigt, auch wenn der Benutzer ein Mitglied der lokalen Administratorgruppe ist, da auch Administratoren mit den Rechten von Standardbenutzern agieren, bis eine Anwendung oder Systemkomponente, für die Administratorberechtigungen erforderlich sind, die Ausführungserlaubnis anfordert.

<a name="Tasks_Requiring_Higher_Privileges"></a>

## <a name="tasks-requiring-higher-privileges"></a>Aufgaben, für die erhöhte Rechte erforderlich sind

Wenn ein Benutzer versucht, eine Aufgabe auszuführen, für die Administratorberechtigungen erforderlich sind, zeigt [!INCLUDE[TLA2#tla_winvista](../../../includes/tla2sharptla-winvista-md.md)] ein Dialogfeld an, das den Benutzer um seine Zustimmung zur weiteren Ausführung bittet. Dieses Dialogfeld ist gegen prozessübergreifenden Datenaustausch geschützt, sodass Schadsoftware keine Benutzereingaben simulieren kann. Analog dazu kann auch auf den Anmeldebildschirm auf dem Desktop nicht durch andere Prozesse zugegriffen werden.

Benutzeroberflächenautomatisierungs-Clients müssen mit anderen Prozessen kommunizieren, von denen einige möglicherweise mit erhöhten Rechten ausgeführt werden. Darüber hinaus benötigen Clients möglicherweise Zugriff auf die Systemdialogfelder, die für andere Prozesse normalerweise nicht sichtbar sind. Daher müssen [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Clients aus Sicht des Systems als vertrauenswürdig eingestuft sein und mit besonderen Berechtigungen ausgeführt werden.

Damit sie für den Datenaustausch mit Anwendungen, die mit höheren Berechtigungsstufen ausgeführt werden, als vertrauenswürdig angesehen werden, müssen Anwendungen signiert sein.

<a name="Manifest_Files"></a>

## <a name="manifest-files"></a>Manifestdateien

Für den Zugriff auf die Benutzeroberfläche des geschützten Systems müssen Anwendungen wie folgt mit einer Manifest-Datei erstellt `uiAccess` werden, die `requestedExecutionLevel` das-Attribut im-Tag enthält:

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

`uiAccess`ist standardmäßig "false"; Das heißt, wenn das Attribut ausgelassen wird oder kein Manifest für die Assembly vorhanden ist, kann die Anwendung keinen Zugriff auf die geschützte Benutzeroberfläche erhalten.
