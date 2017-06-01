---
title: "Runtime Callable Wrapper | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "COM interop, COM wrappers"
  - "RCW"
  - "COM wrappers"
  - "runtime callable wrappers"
  - "interoperation with unmanaged code, COM wrappers"
ms.assetid: 7e542583-1e31-4e10-b523-8cf2f29cb4a4
caps.latest.revision: 9
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 9
---
# Runtime Callable Wrapper
Die Common Language Runtime macht COM\-Objekte über einen Proxy verfügbar, der RCW \(Runtime Callable Wrapper, Aufrufwrapper der Common Language Runtime\) genannt wird.  Obwohl .NET\-Clients einen RCW als normales Objekt betrachten, besteht seine primäre Funktion im Marshallen von Aufrufen zwischen einem .NET\-Client und einem COM\-Objekt.  
  
 Die Common Language Runtime erstellt genau einen RCW für jedes COM\-Objekt, unabhängig von der Anzahl der vorhandenen Verweise auf das Objekt.  Die Common Language Runtime verwaltet für jedes Objekt einen einzelnen RCW pro Prozess.  Wenn Sie einen RCW in einer Anwendungsdomäne oder einem Apartment erstellen und anschließend einen Verweis an eine andere Anwendungsdomäne oder ein anderes Apartment übergeben, wird ein Proxy für das erste Objekt verwendet.  Wie die folgende Abbildung zeigt, kann eine beliebige Anzahl verwalteter Clients auf die COM\-Objekte verweisen, welche die Schnittstellen "INew" und "INewer" verfügbar machen.  
  
 ![RCW](../../../docs/framework/interop/media/rcw.gif "rcw")  
Zugriff auf COM\-Objekte über den RCW  
  
 Mithilfe von Metadaten, die aus einer Typbibliothek abgeleitet werden, erstellt die Common Language Runtime sowohl das aufzurufende COM\-Objekt als auch einen Wrapper für dieses Objekt.  Jeder RCW verwaltet einen Cache von Schnittstellenzeigern auf das umschlossene COM\-Objekt. Ist der RCW nicht länger erforderlich, wird der jeweilige Verweis auf das COM\-Objekt freigegeben.  Die Common Language Runtime führt eine Garbage Collection für den RCW durch.  
  
 Unter anderem marshallt der RCW für das umschlossene Objekt Daten zwischen verwaltetem und nicht verwaltetem Code.  Insbesondere marshallt der RCW Methodenargumente und von Methoden zurückgegebene Werte, wenn der Client und der Server die untereinander ausgetauschten Daten unterschiedlich darstellen.  
  
 Der Standardwrapper erzwingt integrierte Marshallregeln.  Wenn beispielsweise ein .NET\-Client einen Zeichenfolgetyp als Teil eines Arguments an ein nicht verwaltetes Objekt übergibt, konvertiert der Wrapper die Zeichenfolge in einen BSTR\-Typ.  Gibt das COM\-Objekt seinem verwalteten Aufrufer einen BSTR zurück, erhält der Aufrufer eine Zeichenfolge.  Sowohl der Client als auch der Server senden und empfangen auf diese Weise Daten, die ihnen jeweils vertraut sind.  Andere Typen erfordern keine Konvertierung.  Ein Standardwrapper überträgt z. B. eine ganze Zahl von 4 Byte zwischen verwaltetem und nicht verwaltetem Code immer ohne Typkonvertierung.  
  
## Marshallen von ausgewählten Schnittstellen  
 Die Hauptaufgabe des RCW \([Runtime Callable Wrapper](../../../docs/framework/interop/runtime-callable-wrapper.md)\) besteht darin, die Unterschiede zwischen den verwalteten und nicht verwalteten Programmiermodellen unsichtbar zu machen.  Um einen nahtlosen Übergang zu gewährleisten, beansprucht der RCW ausgewählte COM\-Schnittstellen, ohne diese für den .NET\-Client verfügbar zu machen. Dies ist in der folgenden Abbildung dargestellt.  
  
 ![RCW mit Schnittstellen](../../../docs/framework/interop/media/rcwwithinterfaces.gif "rcwwithinterfaces")  
COM\-Schnittstellen und der RCW  
  
 Ein RCW, der als früh gebundenes Objekt erstellt wurde, stellt einen bestimmten Typ dar.  Dieser implementiert die Schnittstellen für das COM\-Objekt und macht die Methoden, Eigenschaften und Ereignisse der Schnittstellen des Objekts verfügbar.  In der Abbildung macht der RCW die Schnittstelle "INew" verfügbar, beansprucht jedoch die Schnittstellen **IUnknown** und **IDispatch**.  Darüber hinaus macht der RCW dem .NET\-Client alle Member der Schnittstelle "INew" verfügbar.  
  
 Der RCW beansprucht die in der folgenden Tabelle aufgelisteten Schnittstellen, die durch das umschlossene Objekt verfügbar gemacht werden.  
  
|Schnittstelle|Beschreibung|  
|-------------------|------------------|  
|**IDispatch**|Regelt späte Bindung an COM\-Objekte durch Reflektion.|  
|**IErrorInfo**|Stellt eine Textbeschreibung des Fehlers und der Fehlerquelle, eine Hilfedatei, den Hilfekontext und die GUID der Schnittstelle bereit, die den Fehler definiert hat \(bei .NET\-Klassen immer **GUID\_NULL**\).|  
|**IProvideClassInfo**|Wenn das umschlossene COM\-Objekt **IProvideClassInfo** implementiert, extrahiert der RCW die Typinformation aus dieser Schnittstelle, um eine bessere Typidentität bereitzustellen.|  
|**IUnknown**|Wird für Objektidentität, Typkoersion und Verwaltung der Lebensdauer verwendet:<br /><br /> -   Objektidentität<br />     Die Common Language Runtime unterscheidet zwischen COM\-Objekten, indem der Wert der Schnittstelle **IUnknown** für jedes Objekt verglichen wird.<br />-   Typkoersion<br />     Der RCW erkennt die dynamische Typermittlung, die durch die **QueryInterface**\-Methode ausgeführt wird.<br />-   Verwaltung der Lebensdauer<br />     Mithilfe der **QueryInterface**\-Methode erhält der RCW einen Verweis auf ein nicht verwaltetes Objekt und hält diesen aufrecht, bis die Common Language Runtime eine Garbage Collection auf den Wrapper durchführt. Dadurch wird das nicht verwaltete Objekt freigegeben.|  
  
 Der RCW beansprucht optional die in der folgenden Tabelle aufgelisteten Schnittstellen, die durch das umschlossene Objekt verfügbar gemacht werden.  
  
|Schnittstelle|Beschreibung|  
|-------------------|------------------|  
|**IConnectionPoint** und **IConnectionPointContainer**|Der RCW konvertiert Objekte, die Ereignisformate für Verbindungspunkte gegenüber delegatbasierten Ereignissen verfügbar machen.|  
|**IDispatchEx**|Wenn die Klasse **IDispatchEx** implementiert, implementiert der RCW **IExpando**.  Die **IDispatchEx**\-Schnittstelle ist eine Erweiterung der **IDispatch**\-Schnittstelle. Im Gegensatz zu **IDispatch** ermöglicht diese Schnittstelle Enumeration, Hinzufügung, Löschen und den Aufruf von Membern unter Berücksichtigung von Groß\-\/Kleinschreibung.|  
|**IEnumVARIANT**|Aktiviert COM\-Typen, die die Behandlung von Enumerationen als Auflistungen unterstützen.|  
  
## Siehe auch  
 [COM Wrappers](../../../docs/framework/interop/com-wrappers.md)   
 [Marshaling Selected Interfaces](http://msdn.microsoft.com/de-de/fdb97fd0-f694-4832-bf15-a4e7cf413840)   
 [COM Callable Wrapper](../../../docs/framework/interop/com-callable-wrapper.md)   
 [Type Library to Assembly Conversion Summary](http://msdn.microsoft.com/de-de/bf3f90c5-4770-4ab8-895c-3ba1055cc958)   
 [Importing a Type Library as an Assembly](../../../docs/framework/interop/importing-a-type-library-as-an-assembly.md)