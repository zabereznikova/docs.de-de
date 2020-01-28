---
title: Richtlinieneinstellungen für die Laufzeitanweisung
ms.date: 03/30/2017
ms.assetid: cb52b1ef-47fd-4609-b69d-0586c818ac9e
ms.openlocfilehash: 7a8933decaec45e8000f3f3d1717847f333deddd
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76738505"
---
# <a name="runtime-directive-policy-settings"></a>Richtlinieneinstellungen für die Laufzeitanweisung

> [!NOTE]
> Dieses Thema bezieht sich auf die .NET Native Developer Preview, ein Vorabrelease der Software. Sie können die Vorschau von der [Microsoft Connect-Website](https://go.microsoft.com/fwlink/?LinkId=394611) herunterladen (Registrierung erforderlich).

Laufzeitanweisungs-Richtlinieneinstellungen für .NET Native bestimmen die Verfügbarkeit von Metadaten für Typen und Typmember zur Laufzeit. Ohne die erforderlichen Metadaten können Vorgänge, die auf Reflektion, Serialisierung und Deserialisierung oder Marshalling von .NET Framework-Typen zu COM oder Windows-Runtime beruhen, fehlschlagen und eine Ausnahme auslösen. Die häufigsten Ausnahmen sind [MissingMetadataException](missingmetadataexception-class-net-native.md) und (im Fall von Interop) [MissingInteropDataException](missinginteropdataexception-class-net-native.md).

Laufzeitrichtlinieneinstellungen werden über eine Laufzeitdirektivendatei (*.rd.xml) gesteuert. Jede Laufzeitanweisung definiert Richtlinien für ein bestimmtes Programmelement, z.B. eine Assembly (das [\<Assembly>](assembly-element-net-native.md)-Element), einen Typ (das [\<Type>](type-element-net-native.md)-Element) oder eine Methode (das [\<Method>](method-element-net-native.md)-Element). Die Anweisung enthält ein oder mehrere Attribute, die die Reflektionsrichtlinientypen, die Serialisierungsrichtlinientypen und die Interop-Richtlinientypen definieren, die im nächsten Abschnitt erläutert werden. Der Wert des Attributs definiert die Richtlinieneinstellung.

## <a name="policy-types"></a>Richtlinientypen

In Laufzeitdirektivendateien werden drei Kategorien von Richtlinientypen erkannt: Reflektion, Serialisierung und Interop.

- Reflektionsrichtlinientypen bestimmen, welche Metadaten zur Laufzeit für Reflektion zur Verfügung gestellt werden:

  - `Activate` steuert den Laufzeitzugriff auf Konstruktoren, um die Aktivierung von Instanzen zu ermöglichen.

  - `Browse` steuert das Abfragen von Informationen über Programmelemente.

  - `Dynamic` steuert den Laufzeitzugriff auf alle Typen und Member, um dynamische Programmierung zu ermöglichen.

  In der folgenden Tabelle sind die Reflektionsrichtlinientypen und die Programmelemente aufgeführt, mit denen sie verwendet werden können.

  |Element|Activate|Durchsuchen|Dynamic|
  |-------------|--------------|------------|-------------|
  |[\<Anwendung>](application-element-net-native.md)|✔️|✔️|✔️|
  |[\<Assembly>](assembly-element-net-native.md)|✔️|✔️|✔️|
  |[\<AttributeImplies>](attributeimplies-element-net-native.md)|✔️|✔️|✔️|
  |[\<Event>](event-element-net-native.md)||✔️|✔️|
  |[\<Field>](field-element-net-native.md)||✔️|✔️|
  |[\<GenericParameter>](genericparameter-element-net-native.md)|✔️|✔️|✔️|
  |[\<ImpliesType>](impliestype-element-net-native.md)|✔️|✔️|✔️|
  |[\<Method>](method-element-net-native.md)||✔️|✔️|
  |[\<MethodInstantiation>](methodinstantiation-element-net-native.md)||✔️|✔️|
  |[\<Namespace>](namespace-element-net-native.md)|✔️|✔️|✔️|
  |[\<Parameter>](parameter-element-net-native.md)|✔️|✔️|✔️|
  |[\<Property>](property-element-net-native.md)||✔️|✔️|
  |[\<Subtypes>](subtypes-element-net-native.md)|✔️|✔️|✔️|
  |[\<Type>](type-element-net-native.md)|✔️|✔️|✔️|
  |[\<TypeInstantiation>](typeinstantiation-element-net-native.md)|✔️|✔️|✔️|
  |[\<TypeParameter>](typeparameter-element-net-native.md)|✔️|✔️|✔️|

- Serialisierungsrichtlinientypen bestimmen, welche Metadaten zur Laufzeit für Serialisierung und Deserialisierung zur Verfügung gestellt werden:

  - `Serialize` steuert den Laufzeitzugriff auf Konstruktoren, Felder und Eigenschaften, um die Serialisierung von Typinstanzen durch Bibliotheken von Drittanbietern wie das Newtonsoft JSON-Serialisierungsprogramm zu ermöglichen.

  - `DataContractSerializer` steuert den Laufzeitzugriff auf Konstruktoren, Felder und Eigenschaften, um die Serialisierung von Typinstanzen durch die <xref:System.Runtime.Serialization.DataContractSerializer>-Klasse zu ermöglichen.

  - `DataContractJsonSerializer` steuert den Laufzeitzugriff auf Konstruktoren, Felder und Eigenschaften, um die Serialisierung von Typinstanzen durch die <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>-Klasse zu ermöglichen.

  - `XmlSerializer` steuert den Laufzeitzugriff auf Konstruktoren, Felder und Eigenschaften, um die Serialisierung von Typinstanzen durch die <xref:System.Xml.Serialization.XmlSerializer>-Klasse zu ermöglichen.

  In der folgenden Tabelle sind die Serialisierungsrichtlinientypen und die Programmelemente aufgeführt, mit denen sie verwendet werden können.

  |Element|Serialisieren|DataContractSerializer|DataContractJsonSerializer|XmlSerializer|
  |-------------|---------------|----------------------------|--------------------------------|-------------------|
  |[\<Anwendung>](application-element-net-native.md)|✔️|✔️|✔️|✔️|
  |[\<Assembly>](assembly-element-net-native.md)|✔️|✔️|✔️|✔️|
  |[\<AttributeImplies>](attributeimplies-element-net-native.md)|✔️|✔️|✔️|✔️|
  |[\<Event>](event-element-net-native.md)|||||
  |[\<Field>](field-element-net-native.md)|✔️||||
  |[\<GenericParameter>](genericparameter-element-net-native.md)|✔️|✔️|✔️|✔️|
  |[\<ImpliesType>](impliestype-element-net-native.md)|✔️|✔️|✔️|✔️|
  |[\<Method>](method-element-net-native.md)|||||
  |[\<MethodInstantiation>](methodinstantiation-element-net-native.md)|||||
  |[\<Namespace>](namespace-element-net-native.md)|✔️|✔️|✔️|✔️|
  |[\<Parameter>](parameter-element-net-native.md)|✔️|✔️|✔️|✔️|
  |[\<Property>](property-element-net-native.md)|✔️||||
  |[\<Subtypes>](subtypes-element-net-native.md)|✔️|✔️|✔️|✔️|
  |[\<Type>](type-element-net-native.md)|✔️|✔️|✔️|✔️|
  |[\<TypeInstantiation>](typeinstantiation-element-net-native.md)|✔️|✔️|✔️|✔️|
  |[\<TypeParameter>](typeparameter-element-net-native.md)|✔️|✔️|✔️|✔️|

- Interop-Richtlinientypen bestimmen, welche Metadaten zur Laufzeit verfügbar gemacht werden, um Verweistypen, Werttypen und Funktionszeiger an COM und Windows-Runtime zu übergeben:

  - `MarshalObject` steuert das systemeigene Marshalling an COM und Windows-Runtime für Verweistypen.

  - `MarshalDelegate` steuert das systemeigene Marshalling von Delegattypen als Funktionszeiger.

  - `MarshalStructure` steuert das systemeigene Marshalling an COM und Windows-Runtime für Werttypen.

  In der folgenden Tabelle sind die Interop-Richtlinientypen und die Programmelemente aufgeführt, mit denen sie verwendet werden können.

  |Element|MarshalObject|MarshalDelegate|MarshalStructure|
  |-------------|-------------------|---------------------|----------------------|
  |[\<Anwendung>](application-element-net-native.md)|✔️|✔️|✔️|
  |[\<Assembly>](assembly-element-net-native.md)|✔️|✔️|✔️|
  |[\<AttributeImplies>](attributeimplies-element-net-native.md)|✔️|✔️|✔️|
  |[\<Event>](event-element-net-native.md)||||
  |[\<Field>](field-element-net-native.md)||||
  |[\<GenericParameter>](genericparameter-element-net-native.md)|✔️|✔️|✔️|
  |[\<ImpliesType>](impliestype-element-net-native.md)|✔️|✔️|✔️|
  |[\<Method>](method-element-net-native.md)||||
  |[\<MethodInstantiation>](methodinstantiation-element-net-native.md)||||
  |[\<Namespace>](namespace-element-net-native.md)|✔️|✔️|✔️|
  |[\<Parameter>](parameter-element-net-native.md)|✔️|✔️|✔️|
  |[\<Property>](property-element-net-native.md)||||
  |[\<Subtypes>](subtypes-element-net-native.md)|✔️|✔️|✔️|
  |[\<Type>](type-element-net-native.md)|✔️|✔️|✔️|
  |[\<TypeInstantiation>](typeinstantiation-element-net-native.md)|✔️|✔️|✔️|
  |[\<TypeParameter>](typeparameter-element-net-native.md)|✔️|✔️|✔️|

## <a name="policy-settings"></a>Richtlinieneinstellungen

Jeder Richtlinientyp kann auf einen der in der folgenden Tabelle aufgeführten Werte festgelegt werden. Beachten Sie, dass Elemente, die Typmember darstellen, einen anderen Satz von Richtlinieneinstellungen unterstützen als andere Elemente.

|Richtlinieneinstellung|Beschreibung|`Assembly`-, `Namespace`-, `Type`- und `TypeInstantiation`-Elemente|`Event`-, `Field`-, `Method`-, `MethodInstantiation`- und `Property`-Elemente|
|--------------------|-----------------|-----------------------------------------------------------------------|--------------------------------------------------------------------------------|
|`All`|Aktiviert die Richtlinie für alle Typen und Member, die die .NET Native-Toolkette nicht entfernt.|✔️||
|`Auto`|Gibt an, dass die Standardrichtlinie für den Richtlinientyp für dieses Programmelement verwendet werden soll. Dies entspricht dem Auslassen einer Richtlinie für diesen Richtlinientyp. `Auto` wird normalerweise verwendet, um anzugeben, dass die Richtlinie von einem übergeordneten Element geerbt wird.|✔️|✔️|
|`Excluded`|Gibt an, dass die Richtlinie für ein bestimmtes Programmelement deaktiviert ist. Beispiel: Die Laufzeitanweisung:<br /><br /> `<Type Name="BusinessClasses.Person" Browse="Excluded" Dynamic="Excluded" />`<br /><br /> gibt an, dass die Metadaten für die `BusinessClasses.Person`-Klasse zum Durchsuchen oder zum dynamischen Instanziieren und Ändern von `Person`-Objekten nicht verfügbar sind.|✔️|✔️|
|`Included`|Aktiviert eine Richtlinie, wenn Metadaten für den übergeordneten Typ verfügbar sind.||✔️|
|`Public`|Aktiviert die Richtlinie für öffentliche Typen oder Member, sofern die Toolkette nicht bestimmt, dass der Typ oder Member unnötig ist und daher entfernt wird. Diese Einstellung unterscheidet sich von der Einstellung `Required Public`, durch die sichergestellt wird, dass Metadaten für öffentliche Typen und Member immer verfügbar sind, auch wenn die Toolkette bestimmt, dass sie nicht erforderlich sind.|✔️||
|`PublicAndInternal`|Aktiviert die Richtlinie für öffentliche und interne Typen oder Member, sofern die Toolkette nicht bestimmt, dass der Typ oder Member unnötig ist und daher entfernt wird. Diese Einstellung unterscheidet sich von der Einstellung `Required PublicAndInternal`, durch die sichergestellt wird, dass Metadaten für öffentliche und interne Typen und Member immer verfügbar sind, auch wenn die Toolkette bestimmt, dass sie nicht erforderlich sind.|✔️||
|`Required`|Gibt an, dass die Richtlinie für einen Member aktiviert ist und Metadaten verfügbar sind, selbst wenn der Member anscheinend verwendet wird.||✔️|
|`Required Public`|Aktiviert die Richtlinie für öffentliche Typen oder Member und stellt sicher, dass die Metadaten für öffentliche Typen und Member immer verfügbar sind. Diese Einstellung unterscheidet sich von der Einstellung `Public`, durch die Metadaten für öffentliche Typen und Member nur verfügbar gemacht werden, wenn die Toolkette bestimmt, dass es erforderlich ist.|✔️||
|`Required PublicAndInternal`|Aktiviert die Richtlinie für öffentliche und interne Typen oder Member und stellt sicher, dass die Metadaten für öffentliche und interne Typen und Member immer verfügbar sind. Diese Einstellung unterscheidet sich von der Einstellung `PublicAndInternal`, durch die Metadaten für öffentliche und interne Typen und Member nur verfügbar gemacht werden, wenn die Toolkette bestimmt, dass es erforderlich ist.|✔️||
|`Required All`|Fordert, dass die Toolkette alle Typen und Member unabhängig von ihrer Verwendung beibehält, und aktiviert die Richtlinie für diese.|✔️||

## <a name="see-also"></a>Siehe auch

- [Runtime Directives (rd.xml) Configuration File Reference (Referenz zur Laufzeitanweisungs-Konfigurationsdatei (rd.xml))](runtime-directives-rd-xml-configuration-file-reference.md)
- [Elemente der Laufzeitanweisung](runtime-directive-elements.md)
