---
title: 'Fehler beim Initialisieren von .NET Framework: Verwalten der Benutzerfreundlichkeit'
ms.date: 03/30/2017
helpviewer_keywords:
- no framework found experience
- initialization errors [.NET Framework]
- .NET Framework, initialization errors
ms.assetid: 680a7382-957f-4f6e-b178-4e866004a07e
ms.openlocfilehash: 73a0ffd4a39b144a61bf559ac424414728fb9a3f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "75716455"
---
# <a name="net-framework-initialization-errors-managing-the-user-experience"></a>Fehler beim Initialisieren von .NET Framework: Verwalten der Benutzerfreundlichkeit

Das Aktivierungssystem der CLR (Common Language Runtime) bestimmt die Version der CLR, die verwendet wird, um verwalteten Anwendungscode auszuführen. In einigen Fällen ist das Aktivierungssystem eventuell nicht in der Lage, eine Version der CLR zu suchen und zu laden. Diese Situation tritt in der Regel auf, wenn eine Anwendung eine CLR-Version erfordert, die ungültig oder nicht auf einem Computer installiert ist. Wenn die angeforderte Version nicht gefunden wird, gibt das CLR-Aktivierungssystem einen HRESULT-Fehlercode von der aufgerufenen Funktion oder Schnittstelle zurück und zeigt dem Benutzer, der die Anwendung ausführt, eventuell eine Fehlermeldung an. Dieser Artikel enthält eine Liste von HRESULT-Codes und beschreibt, wie Sie die Anzeige der Fehlermeldung verhindern können.

Die CLR stellt die Protokollierungsinfrastruktur bereit, die Ihnen helfen wird, CLR-Aktivierungsprobleme zu debuggen. Diese Vorgehensweise wird im Artikel [How to Debug CLR Activation Issues (Debuggen von CLR-Aktivierungsproblemen)](how-to-debug-clr-activation-issues.md) beschrieben. Die Infrastruktur darf nicht mit [Assemblybindungsprotokollen](../tools/fuslogvw-exe-assembly-binding-log-viewer.md) verwechselt werden. Bei diesen handelt es sich um einen vollständig anderen Protokolltyp.

## <a name="clr-activation-hresult-codes"></a>CLR-Aktivierungscodes (HRESULT)

Die CLR-Aktivierung APIs geben HRESULT-Code zurück, um das Ergebnis einer Aktivierung an einen Host zu melden. CLR-Hosts sollten diese Rückgabewerte immer nachschlagen, bevor sie zusätzliche Vorgängen fortsetzen.

- CLR_E_SHIM_RUNTIMELOAD

- CLR_E_SHIM_RUNTIMEEXPORT

- CLR_E_SHIM_INSTALLROOT

- CLR_E_SHIM_INSTALLCOMP

- CLR_E_SHIM_LEGACYRUNTIMEALREADYBOUND

- CLR_E_SHIM_SHUTDOWNINPROGRESS

## <a name="ui-for-initialization-errors"></a>Benutzeroberfläche für Initialisierungsfehler

Wenn das CLR-Aktivierungssystem die richtige Version der Laufzeit, die von einer Anwendung benötigt wird, nicht laden kann, wird eine Fehlermeldung angezeigt. Diese informiert den Benutzer darüber, dass der Computer für das Ausführen der Anwendung nicht ordnungsgemäß konfiguriert ist, und bietet eine Möglichkeit, die Situation zu beheben. In dieser Situation wird in der Regel die folgende Fehlermeldung erstellt. Der Benutzer kann **Ja** wählen, um zu einer Microsoft-Website zu wechseln, auf der die richtige .NET Framework-Version für die Anwendung heruntergeladen werden kann.

Dialogfeld ![Fehler beim Initialisieren von .NET Framework](./media/initialization-errors-managing-the-user-experience/initialization-error-dialog.png "Typische Fehlermeldung bei Initialisierungsfehlern")

## <a name="resolving-the-initialization-error"></a>Beheben von Initialisierungsfehlern

Als Entwickler haben Sie eine Vielzahl von Optionen, um die .NET Framework-Initialisierungsfehlermeldung zu steuern. Beispielsweise können Sie ein API-Flag verwenden, um die Anzeige der Meldung zu verhindern. Dies wird im nächsten Abschnitt erläutert. Sie müssen jedoch noch das Problem beheben, das die Anwendung am Laden der angeforderten Laufzeit hindert. Andernfalls wird die Anwendung möglicherweise gar nicht ausgeführt, oder eine bestimmte Funktion ist eventuell nicht verfügbar.

Um das zugrunde liegende Problem zu beheben und die beste Benutzerfreundlichkeit (weniger Fehlermeldungen) bereitzustellen, empfehlen wir Folgendes:

- Für Anwendungen, die auf .NET Framework 3.5 und früher basieren: Konfigurieren Sie Ihre Anwendung so, dass sie .NET Framework 4 oder höher unterstützt. Weitere Informationen finden Sie in dieser [Anleitung](../migration-guide/how-to-configure-an-app-to-support-net-framework-4-or-4-5.md).

- Für Anwendungen, die auf .NET Framework 4 basieren: Installieren Sie das verteilbare. .NET Framework 4-Paket während des Setups der Anwendung. Weitere Informationen finden Sie unter [Bereitstellungshandbuch für Entwickler](deployment-guide-for-developers.md).

## <a name="controlling-the-error-message"></a>Steuerung von Fehlermeldungen

Das Anzeigen einer Fehlermeldung, die kommuniziert, dass eine angeforderte .NET Framework-Version nicht gefunden wurde, kann entweder als ein hilfreicher Dienst oder ein kleines Ärgernis für den Benutzer angesehen werden. In beiden Fällen können Sie diese Benutzeroberfläche steuern, indem Sie Flags an die Aktivierung-API übergeben.

Die [ICLRMetaHostPolicy::GetRequestedRuntime](../unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md)-Methode akzeptiert einen [METAHOST_POLICY_FLAGS](../unmanaged-api/hosting/metahost-policy-flags-enumeration.md)-Enumerationsmember als Eingabe. Sie können das METAHOST_POLICY_SHOW_ERROR_DIALOG-Flag einschließen, um eine Fehlermeldung anzufordern, wenn die angeforderte Version der CLR nicht gefunden wird. Standardmäßig wird die Fehlermeldung nicht angezeigt. (Die [ICLRMetaHost::GetRuntime](../unmanaged-api/hosting/iclrmetahost-getruntime-method.md)-Methode akzeptiert dieses Flag nicht und stellt keine andere Möglichkeit bereit, um die Fehlermeldung anzuzeigen.)

Windows bietet eine [SetErrorMode](/windows/win32/api/errhandlingapi/nf-errhandlingapi-seterrormode)-Funktion, die Sie verwenden können, um zu deklarieren, dass Sie Fehlermeldungen aufgrund des innerhalb des Prozesses ausgeführten Codes angezeigt werden soll. Sie können das SEM_FAILCRITICALERRORS-Flag angeben, um das Anzeigen der Fehlermeldung zu verhindern.

In einigen Szenarios ist es wichtig, die SEM_FAILCRITICALERRORS-Einstellung zu überschreiben, die von einem Anwendungsprozess festgelegt wurde. Wenn Sie beispielsweise über eine systemeigene COM-Komponente verfügen, die die CLR hostet und in einem Prozess gehostet wird, in dem SEM_FAILCRITICALERRORS festgelegt ist, können Sie das Flag in Abhängigkeit von den Auswirkungen der Anzeige von Fehlermeldungen in diesem bestimmten Prozess überschreiben. In diesem Fall können Sie eines der folgenden Flags verwenden, um SEM_FAILCRITICALERRORS zu überschreiben:

- Verwenden Sie METAHOST_POLICY_IGNORE_ERROR_MODE mit der [ICLRMetaHostPolicy::GetRequestedRuntime](../unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md)-Methode.

- Verwenden Sie RUNTIME_INFO_IGNORE_ERROR_MODE mit der [GetRequestedRuntimeInfo](../unmanaged-api/hosting/getrequestedruntimeinfo-function.md)-Funktion.

## <a name="ui-policy-for-clr-provided-hosts"></a>Benutzeroberflächenrichtlinie für von der CLR bereitgestellte Hosts

Die CLR bietet eine Reihe von Hosts für verschiedene Szenarien, und alle diese Hosts zeigen eine Fehlermeldung an, wenn Probleme beim Laden der erforderlichen Laufzeitversion auftreten. Die folgende Tabelle enthält eine Liste von Hosts und deren Fehlermeldungsrichtlinien.

|CLR-Host|Beschreibung|Fehlermeldungsrichtlinie|Kann die Fehlermeldung deaktiviert werden?|
|--------------|-----------------|--------------------------|------------------------------------|
|Verwalteter EXE-Host|Startet verwaltete EXE-Dateien.|Wird im Fall von fehlender .NET Framework-Version angezeigt|Nein|
|Verwalteter COM-Host|Lädt verwalteten COM-Komponenten in einen Prozess.|Wird im Fall von fehlender .NET Framework-Version angezeigt|Ja, durch Festlegen des SEM_FAILCRITICALERRORS-Flags|
|ClickOnce-Host|Startet ClickOnce-Anwendungen.|Wird ab .NET Framework 4.5 im Fall einer fehlenden .NET Framework-Version angezeigt|Nein|
|XBAP-Host|Startet WPF-XBAP-Anwendungen.|Wird ab .NET Framework 4.5 im Fall einer fehlenden .NET Framework-Version angezeigt|Nein|

## <a name="windows-8-behavior-and-ui"></a>Verhalten und Benutzeroberfläche von Windows 8

Das CLR-Aktivierungssystem stellt das gleiche Verhalten und die gleiche Benutzeroberfläche unter Windows 8 bereit, wie auf anderen Versionen des Windows-Betriebssystems, es sei denn, es treten Probleme beim Laden von CLR 2.0 auf. Windows 8 umfasst .NET Framework 4.5, das CLR 4.5 verwendet. Windows 8 umfasst jedoch nicht .NET Framework 2.0, 3.0 oder 3.5, die alle CLR 2.0 verwenden. Daher werden Anwendungen, die von CLR 2.0 abhängen, unter Windows 8 nicht standardmäßig ausgeführt. Stattdessen wird das folgende Dialogfeld angezeigt, um Benutzern die Installation von .NET Framework 3.5 zu ermöglichen. Benutzer können .NET Framework 3.5 auch in der Systemsteuerung aktivieren. Beide Optionen werden im Artikel [Installieren von .NET Framework 3.5 auf Windows 10, Windows 8.1 und Windows 8](../install/dotnet-35-windows-10.md) behandelt.

![Dialogfeld für die Installation von 3.5 auf Windows 8](./media/initialization-errors-managing-the-user-experience/install-framework-on-demand-dialog.png "Aufforderung zum Installieren von .NET Framework 3.5 bei Bedarf")

> [!NOTE]
> .NET Framework 4.5 ersetzt .NET Framework 4 (CLR 4) auf dem Computer des Benutzers. Daher werden .NET Framework 4-Anwendungen nahtlos ausgeführt, ohne dieses Dialogfeld unter Windows 8 anzuzeigen.

Wenn .NET Framework 3.5 installiert ist, können Benutzer Anwendungen, die auf .NET Framework 2.0, 3.0 oder 3.5 angewiesen sind, auf ihren Computern mit Windows 8 ausführen. Sie können .NET Framework 1.0 und 1.1-Anwendungen ausführen, vorausgesetzt, dass diese Anwendungen nicht explizit so konfiguriert wurden, dass sie nur auf .NET Framework 1.0 oder 1.1 ausgeführt werden können. Weitere Informationen finden Sie unter [Migrieren von .NET Framework 1.1](../migration-guide/migrating-from-the-net-framework-1-1.md).

Ab .NET Framework 4.5 wurde die CLR-Aktivierungsprotokollierung verbessert. Sie enthält nun auch Protokolleinträge, die erfassen, wann und warum eine Initialisierungsfehlermeldung angezeigt wird. Weitere Informationen finden Sie unter [Vorgehensweise: Debuggen von CLR-Aktivierungsproblemen](how-to-debug-clr-activation-issues.md).

## <a name="see-also"></a>Siehe auch

- [Bereitstellungshandbuch für Entwickler](deployment-guide-for-developers.md)
- [How to: Konfigurieren einer App zur Unterstützung von .NET Framework 4 oder höher](../migration-guide/how-to-configure-an-app-to-support-net-framework-4-or-4-5.md)
- [How to: Debuggen von CLR-Aktivierungsproblemen](how-to-debug-clr-activation-issues.md)
- [Installieren von .NET Framework 3.5 auf Windows 10, Windows 8.1 und Windows 8](../install/dotnet-35-windows-10.md)
