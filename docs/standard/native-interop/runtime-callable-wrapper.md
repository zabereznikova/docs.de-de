---
title: Runtime Callable Wrapper (RCW)
description: Die CLR macht COM-Objekte über einen Runtime Callable Wrapper verfügbar, der Aufrufe zwischen einem .NET-Client und einem COM-Objekt verwaltet.
ms.date: 03/30/2017
helpviewer_keywords:
- COM interop, COM wrappers
- RCW
- COM wrappers
- runtime callable wrappers
- interoperation with unmanaged code, COM wrappers
ms.assetid: 7e542583-1e31-4e10-b523-8cf2f29cb4a4
ms.openlocfilehash: 9c218fe7a08bd7181d66aa849bcca4cac00dc6fa
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90535858"
---
# <a name="runtime-callable-wrapper"></a>Runtime Callable Wrapper (RCW)
Die Common Language Runtime macht COM-Objekte über einen Proxy verfügbar, der RCW (Runtime Callable Wrapper, Aufrufwrapper der Common Language Runtime) genannt wird. Obwohl .NET-Clients einen RCW als normales Objekt betrachten, besteht seine primäre Funktion im Marshallen von Aufrufen zwischen einem .NET-Client und einem COM-Objekt.  
  
 Die Common Language Runtime erstellt genau einen RCW für jedes COM-Objekt, unabhängig von der Anzahl der vorhandenen Verweise auf das Objekt. Die Common Language Runtime verwaltet für jedes Objekt einen einzelnen RCW pro Prozess.  Wenn Sie einen RCW in einer Anwendungsdomäne oder einem Apartment erstellen und anschließend einen Verweis an eine andere Anwendungsdomäne oder ein anderes Apartment übergeben, wird ein Proxy für das erste Objekt verwendet.  Wie die folgende Abbildung zeigt, kann eine beliebige Anzahl verwalteter Clients auf die COM-Objekte verweisen, welche die Schnittstellen "INew" und "INewer" verfügbar machen.  

Die folgende Abbildung veranschaulicht, wie über den RCW auf COM-Objekte zugegriffen wird:

 ![Zugriff auf COM-Objekte über den RCW](./media/runtime-callable-wrapper/runtime-callable-wrapper.gif)  

 Mithilfe von Metadaten, die aus einer Typbibliothek abgeleitet werden, erstellt die Common Language Runtime sowohl das aufzurufende COM-Objekt als auch einen Wrapper für dieses Objekt. Jeder RCW verwaltet einen Cache von Schnittstellenzeigern auf das umschlossene COM-Objekt. Ist der RCW nicht länger erforderlich, wird der jeweilige Verweis auf das COM-Objekt freigegeben. Die Common Language Runtime führt eine Garbage Collection für den RCW durch.  
  
 Unter anderem marshallt der RCW für das umschlossene Objekt Daten zwischen verwaltetem und nicht verwaltetem Code. Insbesondere marshallt der RCW Methodenargumente und von Methoden zurückgegebene Werte, wenn der Client und der Server die untereinander ausgetauschten Daten unterschiedlich darstellen.  
  
 Der Standardwrapper erzwingt integrierte Marshallregeln. Wenn beispielsweise ein .NET-Client einen Zeichenfolgetyp als Teil eines Arguments an ein nicht verwaltetes Objekt übergibt, konvertiert der Wrapper die Zeichenfolge in einen BSTR-Typ. Gibt das COM-Objekt seinem verwalteten Aufrufer einen BSTR zurück, erhält der Aufrufer eine Zeichenfolge. Sowohl der Client als auch der Server senden und empfangen auf diese Weise Daten, die ihnen jeweils vertraut sind. Andere Typen erfordern keine Konvertierung. Ein Standardwrapper überträgt z. B. eine ganze Zahl von 4 Byte zwischen verwaltetem und nicht verwaltetem Code immer ohne Typkonvertierung.  
  
## <a name="marshaling-selected-interfaces"></a>Marshallen von ausgewählten Schnittstellen  
 Die Hauptaufgabe des RCW ([Runtime Callable Wrapper](runtime-callable-wrapper.md)) besteht darin, die Unterschiede zwischen den verwalteten und nicht verwalteten Programmiermodellen unsichtbar zu machen. Um einen nahtlosen Übergang zu gewährleisten, beansprucht der RCW ausgewählte COM-Schnittstellen, ohne diese für den .NET-Client verfügbar zu machen. Dies ist in der folgenden Abbildung dargestellt.

 Die folgende Abbildung zeigt COM-Schnittstellen und den RCW:
  
 ![Screenshot des RCW mit Schnittstellen](./media/runtime-callable-wrapper/runtime-callable-wrapper-interfaces.gif)  
  
 Ein RCW, der als früh gebundenes Objekt erstellt wurde, stellt einen bestimmten Typ dar. Dieser implementiert die Schnittstellen für das COM-Objekt und macht die Methoden, Eigenschaften und Ereignisse der Schnittstellen des Objekts verfügbar. In der Abbildung macht der RCW die Schnittstelle „INew“ verfügbar, beansprucht jedoch die Schnittstellen **IUnknown** und **IDispatch**. Darüber hinaus macht der RCW dem .NET-Client alle Member der Schnittstelle "INew" verfügbar.  
  
 Der RCW beansprucht die in der folgenden Tabelle aufgelisteten Schnittstellen, die durch das umschlossene Objekt verfügbar gemacht werden.  
  
|Interface|Beschreibung|  
|---------------|-----------------|  
|**IDispatch**|Regelt späte Bindung an COM-Objekte durch Reflektion.|  
|**IErrorInfo**|Stellt eine Textbeschreibung des Fehlers und der Fehlerquelle, eine Hilfedatei, den Hilfekontext und die GUID der Schnittstelle bereit, die den Fehler definiert hat (bei .NET-Klassen immer **GUID_NULL**).|  
|**IProvideClassInfo**|Wenn das COM-Objekt, das umschlossen wird, **IProvideClassInfo** implementiert, extrahiert der RCW die Typinformationen über diese Schnittstelle, um eine bessere Typidentität bereitzustellen.|  
|**IUnknown**|Wird für Objektidentität, Typkoersion und Verwaltung der Lebensdauer verwendet:<br /><br /> – Objektidentität<br />     Die Common Language Runtime unterscheidet zwischen COM-Objekten, indem der Wert der Schnittstelle **IUnknown** für jedes Objekt verglichen wird.<br />– Typkoersion<br />     Der RCW erkennt die dynamische Typermittlung durch die Methode **QueryInterface**.<br />– Verwaltung der Lebensdauer<br />     Mithilfe der Methode **QueryInterface** erhält der RCW einen Verweis auf ein nicht verwaltetes Objekt und hält diesen aufrecht, bis die Common Language Runtime eine Garbage Collection auf den Wrapper durchführt. Dadurch wird das nicht verwaltete Objekt freigegeben.|  
  
 Der RCW beansprucht optional die in der folgenden Tabelle aufgelisteten Schnittstellen, die durch das umschlossene Objekt verfügbar gemacht werden.  
  
|Interface|Beschreibung|  
|---------------|-----------------|  
|**IConnectionPoint** und **IConnectionPointContainer**|Der RCW konvertiert Objekte, die Ereignisformate für Verbindungspunkte gegenüber delegatbasierten Ereignissen verfügbar machen.|  
|**IDispatchEx** (nur .NET Framework) |Wenn die Klasse **IDispatchEx** implementiert, implementiert der RCW **IExpando**. Die **IDispatchEx**-Schnittstelle ist eine Erweiterung der **IDispatch**-Schnittstelle. Im Gegensatz zu **IDispatch** ermöglicht sie das Aufzählen, Hinzufügen, Löschen und Aufrufen von Membern unter Berücksichtigung von Groß-/Kleinschreibung.|  
|**IEnumVARIANT**|Aktiviert COM-Typen, die die Behandlung von Enumerationen als Auflistungen unterstützen.|  
  
## <a name="see-also"></a>Siehe auch

- [COM-Wrapper](com-wrappers.md)
- [COM Callable Wrapper](com-callable-wrapper.md)
- [Zusammenfassung: Konvertieren einer Typbibliothek in eine Assembly](/previous-versions/dotnet/netframework-4.0/k83zzh38(v=vs.100))
- [Importing a Type Library as an Assembly (Importieren einer Typbibliothek als Assembly)](../../framework/interop/importing-a-type-library-as-an-assembly.md)
