---
title: WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)
description: Fasst die .NET Framework nicht verwaltete API Leistungsindikator Informationen zu WMI und Leistung.
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.date: 11/06/2017
ms.topic: article-type-from-white-list
ms.prod: .net-framework
ms.devlang: cpp
ms.workload: dotnet
ms.openlocfilehash: 466ba410f7d6c13eb5f1949bf3aa32c3951a8ba7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="windows-management-instrumentation-wmi-and-performance-counters-unmanaged-api-reference"></a>Windows-Verwaltungsinstrumentation (WMI) und Leistungsindikatoren (Referenz zur nicht verwalteten API)

Die .NET Framework WMI und Leistungsindikatoren nicht verwaltete API besteht aus einem Satz von Funktionen, die Aufrufe zu umschließen die [systemeigene Windows Management Instrumentation API](https://msdn.microsoft.com/library/aa389276(v=vs.85).aspx). Sie können Sie Tools und Bibliotheken, die verwalten und Überwachen von Remotecomputern, zu entwickeln.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
Die API umfasst die folgenden Funktionen:

| Funktion | Beschreibung |
|---------|---------|
| [BeginEnumeration-Funktion](beginenumeration.md) | Setzt den Enumerator auf den Anfang einer Enumeration von Eigenschaften für WMI-Objekts zurück. |
| [BeginMethodEnumeration-Funktion](beginmethodenumeration.md) |  Startet eine Enumeration der Methoden, die für ein Objekt zur Verfügung. |
| [BlessIWbemServices-Funktion](blessiwbemservices.md) | Gibt an, ob die Anmeldeinformationen des Benutzers Zugriff auf eine angegebene IWbemServices Klasse zuzulassen. |
| [BlessIWbemServicesObject-Funktion](blessiwbemservicesobject.md) | Gibt an, ob die Anmeldeinformationen des Benutzers Zugriff auf eine angegebene IWbem Dienstobjekt zuzulassen. |
| [Clone-Funktion](clone.md) | Gibt ein neues Objekt, das eine vollständige Klon des aktuellen Objekts ist. |
| [CloneEnumWbemClassObject-Funktion](cloneenumwbemclassobject.md) | Erstellt eine logische Kopie eines Enumerators, der seiner aktuellen Position in einer Enumeration beibehalten. |
| [CompareTo-Funktion](compareto.md) | Vergleicht ein Objekt in ein anderes Windows-Management-Objekt. |
| [ConnectServerWmi-Funktion](connectserverwmi.md) | Erstellt eine Verbindung über DCOM mit einem WMI-Namespace auf einem angegebenen Computer an. |
| [CreateClassEnumWmi-Funktion](createclassenumwmi.md) | Gibt einen Enumerator für alle Klassen, die die angegebenen Auswahlkriterien entsprechen. |
| [CreateInstanceEnumWmi-Funktion](createinstanceenumwmi.md) | Gibt einen Enumerator, der das bestehen einer bestimmten Klasse, die angegebenen Auswahlkriterien erfüllen zurückgibt. |
| [Delete-Funktion](delete.md) | Löscht eine angegebene Eigenschaft aus einer Klassendefinition und aller seiner Qualifizierer an. |
| [DeleteMethod-Funktion](deletemethod.md) | Löscht eine angegebene Methode aus der Definition einer CIM-Klasse. |
| [EndEnumeration-Funktion](endenumeration.md) | Beendet eine Enumerationsfolge an. | 
| [EndMethodEnumeration-Funktion](endmethodenumeration.md) | Beendet eine Enumerationsfolge gestartet durch Aufrufen der [BeginMethodEnumeration Funktion](beginmethodenumeration.md). |
| [ExecNotificationQueryWmi-Funktion](execnotificationquerywmi.md) | Führt eine Abfrage aus, um Ereignisse zu empfangen. |
| [ExecQueryWmi-Funktion](execquerywmi.md) | Führt eine Abfrage zum Abrufen von Objekten. |
| [FormatFromRawValue-Funktion](formatfromrawvalue.md) | Wenn die formatkonvertierung zeitbasierte ist ein Leistungszählers Datenwert in das angegebene Format oder zwei Leistungszählers Datenwerte konvertiert werden soll. | 
| [Get-Funktion](get.md) | Ruft einen Wert für die angegebene Eigenschaft ab, falls vorhanden. |
| [GetCurrentApartmentType-Funktion](getcurrentapartmenttype.md) | Ruft den Typ des Apartment, in der der Aufrufer ausgeführt wird. |
| [GetDemultiplexedStub-Funktion](getdemultiplexedstub.md) | Erstellt eine Objekt Weiterleitung eine Ereignissenke, bei der ein Client asynchrone Aufrufe von Windows-Verwaltung empfangen. |
| [GetErrorInfo-Funktion](geterrorinfo.md) | Ruft die Fehlerinformationen aus dem vorherigen Funktionsaufruf ab. | 
| [GetMethod-Funktion](getmethod.md) | Ruft Informationen über die angegebene Methode ab. | 
| [GetMethodOrigin-Funktion](getmethodorigin.md) | Bestimmt die Klasse, die in der eine Methode deklariert wird. |
| [GetMethodQualifierSet-Funktion](getmethodqualifierset.md) | Ruft den Qualifizierer für eine bestimmte Methode festgelegt. |
| [GetNames-Funktion](getnames.md) | Ruft eine Teilmenge oder aller der Namen der Eigenschaften eines Objekts ab. |
| [GetObjectText-Funktion](getobjecttext.md) | Gibt ein Text-Rendering eines Objekts in der MOF-Syntax zurück. | 
| [GetPropertyHandle-Funktion](getpropertyhandle.md) | Gibt ein eindeutige-Handle, das eine Eigenschaft identifiziert. |
| [GetPropertyOrigin-Funktion](getpropertyorigin.md) | Bestimmt die Klasse, die in der eine Eigenschaft deklariert wird. |
| [GetPropertyQualifierSet-Funktion](getpropertyqualifierset.md) | Ruft den Qualifizierer, legen Sie für eine bestimmte Eigenschaft ab.  |
| [GetQualifierSet-Funktion](getqualifierset.md) | Ruft den Qualifizierer für die Instanz einer Klasse oder einer Klassendefinition festgelegt. |
| [InheritsFrom-Funktion](inheritsfrom.md) | Bestimmt, ob die aktuelle Klasse oder Instanz aus einer angegebenen übergeordneten Klasse abgeleitet ist. |
| [Initialize-Funktion](initialize.md) | Führt eine WMI-Initialisierung. |
| [Next-Funktion](next.md) | Ruft die nächste Eigenschaft in einer Enumeration ab. | 
| [NextMethod-Funktion](nextmethod.md) | Ruft die nächste Methode in einer Enumeration ab. |
| [Put-Funktion](put.md) | Legt eine benannte Eigenschaft auf einen neuen Wert fest. |
| [PutClassWmi-Funktion](putclasswmi.md) | Eine neue Klasse erstellt oder aktualisiert eine vorhandene. |
| [PutInstanceWmi-Funktion](putinstancewmi.md) | Erstellt oder aktualisiert eine Instanz einer vorhandenen Klasse. Die Instanz wird in das WMI-Repository geschrieben. |
| [PutMethod-Funktion](putmethod.md) | Erstellt eine Methode an. |
| [QualifierSet_BeginEnumeration-Funktion](qualifierset-beginenumeration.md) | Setzt einen Enumerator der Qualifizierer eines Objekts an den Anfang der Enumeration zurück. |
| [QualifierSet_Delete-Funktion](qualifierset-delete.md) | Löscht einen angegebenen Qualifizierer anhand des Namens an.  |
| [QualifierSet_EndEnumeration-Funktion](qualifierset-endenumeration.md) | Beendet die Enumeration, die mit einem Aufruf von begonnen der `QualifierSet_BeginEnumeration` Funktion. |
| [QualifierSet_Get-Funktion](qualifierset-get.md) | Ruft den angegebenen benannten Qualifizierer ab.  |
| [QualifierSet_GetNames-Funktion](qualifierset-getnames.md) | Ruft die Namen des alle-Qualifizierer oder der angegebenen Qualifizierer, die aus dem aktuellen Objekt oder eine Eigenschaft verfügbar sind. |
| [QualifierSet_Next-Funktion](qualifierset-next.md) | Ruft den nächsten Qualifizierer in einer Enumeration, die durch einen Aufruf gestartet der [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md) Funktion. |
| [QualifierSet_Put-Funktion](qualifierset-put.md) | Schreibt die benannte Qualifizierer und Wert. |
| [ResetSecurity-Funktion](resetsecurity.md) | Weist den angegebenen Identitätstoken für den aktuellen Thread. |
| [SetSecurity-Funktion](setsecurity.md) | Ruft das Identitätstoken des aktuellen Threads zugeordnet. |
| [SpawnDerivedClass-Funktion](spawnderivedclass.md) | Erstellt ein Klassenobjekt für die neu abgeleitete aus einem angegebenen Objekt. | 
| [SpawnInstance-Funktion](spawninstance.md) | Erstellt eine neue Instanz einer Klasse an. |   
| [VerifyClient-Funktion](verifyclientkey.md) | Stellt sicher, dass der Clientschlüssel die richtigen Sicherheit verfügt. |
| [WritePropertyValue-Funktion](writepropertyvalue.md) | Schreibt eine angegebene Anzahl von Bytes an eine Eigenschaft, die durch ein Eigenschaftshandle identifiziert. |

 ## <a name="see-also"></a>Siehe auch
[Referenz zur nicht verwalteten API](../index.md) 