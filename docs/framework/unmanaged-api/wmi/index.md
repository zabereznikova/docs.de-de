---
title: WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)
description: Fasst die nicht verwaltete .NET Framework-API für WMI und Informationen zu Leistungsindikatoren zusammen.
ms.date: 11/06/2017
ms.openlocfilehash: f28cd25ee6c3511dc5ac8a6dd4076c81f43fe74a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "73127422"
---
# <a name="windows-management-instrumentation-wmi-and-performance-counters-unmanaged-api-reference"></a>Windows-Verwaltungsinstrumentation (WMI) und Leistungsindikatoren (Referenz zur nicht verwalteten API)

Die .NET Framework-WMI und Leistungsindikatoren für die nicht verwaltete API bestehen aus einer Sammlung von Funktionen, die Aufrufe der [nativen Windows-Verwaltungsinstrumentation-API](/windows/desktop/WmiSdk/com-api-for-wmi) in einen Wrapper einschließen. Sie ermöglichen die Entwicklung von Tools und Bibliotheken, die Remotecomputersysteme verwalten und überwachen.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

Die API umfasst die folgenden Funktionen:

| Funktion | Beschreibung |
|---------|---------|
| [BeginEnumeration-Funktion](beginenumeration.md) | Setzt den Enumerator auf den Anfang einer Enumeration von WMI-Objekteigenschaften zurück. |
| [BeginMethodEnumeration-Funktion](beginmethodenumeration.md) |  Startet eine Enumeration der verfügbaren Methoden für ein Objekt. |
| [BlessIWbemServices-Funktion](blessiwbemservices.md) | Gibt an, ob die Anmeldeinformationen des Benutzers Zugriff auf eine angegebene IWbemServices-Klasse zulassen. |
| [BlessIWbemServicesObject-Funktion](blessiwbemservicesobject.md) | Gibt an, ob die Anmeldeinformationen des Benutzers Zugriff auf ein angegebenes IWbemServices-Dienstobjekt zulassen. |
| [Clone-Funktion](clone.md) | Gibt ein neues Objekt zurück, das ein vollständiger Klon des aktuellen Objekts ist. |
| [CloneEnumWbemClassObject-Funktion](cloneenumwbemclassobject.md) | Erstellt eine logische Kopie eines Enumerators unter Beibehaltung der aktuellen Position in einer Enumeration. |
| [CompareTo-Funktion](compareto.md) | Vergleicht ein Objekt mit einem anderen Windows-Verwaltungsobjekt. |
| [ConnectServerWmi-Funktion](connectserverwmi.md) | Erstellt über DCOM eine Verbindung mit einem WMI-Namespace auf einem angegebenen Computer. |
| [CreateClassEnumWmi-Funktion](createclassenumwmi.md) | Gibt einen Enumerator für alle Klassen zurück, die die angegebenen Auswahlkriterien erfüllen. |
| [CreateInstanceEnumWmi-Funktion](createinstanceenumwmi.md) | Gibt einen Enumerator zurück, der die Instanzen einer bestimmten Klasse zurückgibt, die angegebene Auswahlkriterien erfüllen. |
| [Delete-Funktion](delete.md) | Löscht eine angegebene Eigenschaft aus einer Klassendefinition sowie alle ihre Qualifizierer. |
| [DeleteMethod-Funktion](deletemethod.md) | Löscht eine angegebene Methode aus einer CIM-Klassendefinition. |
| [EndEnumeration-Funktion](endenumeration.md) | Beendet eine Enumerationssequenz. |
| [EndMethodEnumeration-Funktion](endmethodenumeration.md) | Beendet eine Enumerationssequenz, die durch den Aufruf der [BeginMethodEnumeration-Funktion](beginmethodenumeration.md) gestartet wurde. |
| [ExecNotificationQueryWmi-Funktion](execnotificationquerywmi.md) | Führt eine Abfrage zum Empfangen von Ereignissen aus. |
| [ExecQueryWmi-Funktion](execquerywmi.md) | Führt eine Abfrage zum Abrufen von Objekten aus. |
| [FormatFromRawValue-Funktion](formatfromrawvalue.md) | Konvertiert einen Rohdatenleistungswert in das angegebene Format oder zwei Rohdatenleistungswerte, wenn die Formatkonvertierung zeitabhängig ist. |
| [Get-Funktion](get.md) | Ruft einen angegebenen Eigenschaftswert ab, wenn dieser vorhanden ist. |
| [GetCurrentApartmentType-Funktion](getcurrentapartmenttype.md) | Ruft den Typ des Apartments ab, in dem die aufrufende Funktion ausgeführt wird. |
| [GetDemultiplexedStub-Funktion](getdemultiplexedstub.md) | Erstellt eine Objektweiterleitungssenke, um einen Client beim Empfang asynchroner Aufrufe von der Windows-Verwaltung zu unterstützen. |
| [GetErrorInfo-Funktion](geterrorinfo.md) | Ruft Fehlerinformationen aus dem vorherigen Funktionsaufruf ab. |
| [GetMethod-Funktion](getmethod.md) | Ruft Informationen zur angegebenen Methode ab. |
| [GetMethodOrigin-Funktion](getmethodorigin.md) | Bestimmt die Klasse, in der eine Methode deklariert wird. |
| [GetMethodQualifierSet-Funktion](getmethodqualifierset.md) | Ruft den Qualifizierer ab, der für eine bestimmte Methode festgelegt ist. |
| [GetNames-Funktion](getnames.md) | Ruft eine Teilmenge oder alle Namen der Eigenschaften eines Objekts ab. |
| [GetObjectText-Funktion](getobjecttext.md) | Gibt ein Textrendering eines Objekts in der MOF-Syntax zurück. |
| [GetPropertyHandle-Funktion](getpropertyhandle.md) | Gibt ein eindeutiges Handle zurück, das eine Eigenschaft identifiziert. |
| [GetPropertyOrigin-Funktion](getpropertyorigin.md) | Bestimmt die Klasse, in der eine Eigenschaft deklariert wird. |
| [GetPropertyQualifierSet-Funktion](getpropertyqualifierset.md) | Ruft den Qualifizierer ab, der für eine bestimmte Eigenschaft festgelegt ist.  |
| [GetQualifierSet-Funktion](getqualifierset.md) | Ruft den Qualifizierer ab, der für eine Klasseninstanz oder eine Klassendefinition festgelegt ist. |
| [InheritsFrom-Funktion](inheritsfrom.md) | Bestimmt, ob die aktuelle Klasse oder Instanz aus einer angegebenen übergeordneten Klasse abgeleitet ist. |
| [Initialize-Funktion](initialize.md) | Führt die WMI-Initialisierung aus. |
| [Next-Funktion](next.md) | Ruft die nächste Eigenschaft in einer Enumeration ab. |
| [NextMethod-Funktion](nextmethod.md) | Ruft die nächste Methode in einer Enumeration ab. |
| [Put-Funktion](put.md) | Legt eine benannte Eigenschaft auf einen neuen Wert fest. |
| [PutClassWmi-Funktion](putclasswmi.md) | Erstellt eine neue Klasse oder aktualisiert eine vorhandene Klasse. |
| [PutInstanceWmi-Funktion](putinstancewmi.md) | Erstellt oder aktualisiert eine Instanz einer vorhandenen Klasse. Die Instanz wird in das WMI-Repository geschrieben. |
| [PutMethod-Funktion](putmethod.md) | Erstellt eine Methode. |
| [QualifierSet_BeginEnumeration-Funktion](qualifierset-beginenumeration.md) | Setzt einen Enumerator der Qualifizierer eines Objekts auf den Anfang der Enumeration zurück. |
| [QualifierSet_Delete-Funktion](qualifierset-delete.md) | Löscht einen angegebenen Qualifizierer anhand des Namens.  |
| [QualifierSet_EndEnumeration-Funktion](qualifierset-endenumeration.md) | Beendet die Enumeration, die mit einem Aufruf der `QualifierSet_BeginEnumeration`-Funktion gestartet wurde. |
| [QualifierSet_Get-Funktion](qualifierset-get.md) | Ruft den angegebenen benannten Qualifizierer ab.  |
| [QualifierSet_GetNames-Funktion](qualifierset-getnames.md) | Ruft die Namen aller Qualifizierer oder von angegebenen Qualifizierern ab, die aus dem aktuellen Objekt oder der aktuellen Eigenschaft verfügbar sind. |
| [QualifierSet_Next-Funktion](qualifierset-next.md) | Ruft den nächsten Qualifizierer in einer Enumeration ab, die durch einen Aufruf der [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md)-Funktion gestartet wurde. |
| [QualifierSet_Put-Funktion](qualifierset-put.md) | Schreibt den benannten Qualifizierer und den Wert. |
| [ResetSecurity-Funktion](resetsecurity.md) | Weist das angegebene Identitätswechseltoken dem aktuellen Thread zu. |
| [SetSecurity-Funktion](setsecurity.md) | Ruft das Identitätswechseltoken ab, das dem aktuellen Thread zugeordnet ist. |
| [SpawnDerivedClass-Funktion](spawnderivedclass.md) | Erstellt ein neu abgeleitetes Klassenobjekt aus einem angegebenen Objekt. |
| [SpawnInstance-Funktion](spawninstance.md) | Erstellt eine neue Instanz einer Klasse. |
| [VerifyClient-Funktion](verifyclientkey.md) | Stellt sicher, dass der Clientschlüssel die richtige Sicherheit aufweist. |
| [WritePropertyValue-Funktion](writepropertyvalue.md) | Schreibt eine angegebene Anzahl von Bytes in eine Eigenschaft, die durch ein Eigenschaftenhandle identifiziert wird. |

## <a name="see-also"></a>Weitere Informationen

- [Referenz zur nicht verwalteten API](../index.md)
