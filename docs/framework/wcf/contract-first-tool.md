---
title: Vertrag zuerst-Tool
ms.date: 03/30/2017
ms.assetid: 0a880690-f460-4475-a5f4-9f91ce08fcc6
ms.openlocfilehash: 36e1a3e19f802ca5b74cf50f5bcd57c167e31e33
ms.sourcegitcommit: e48a54ebe62e874500a7043f6ee0b77a744d55b4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/26/2020
ms.locfileid: "80291705"
---
# <a name="contract-first-tool"></a>Vertrag zuerst-Tool
Dienstverträge müssen häufig aus vorhandenen Diensten erstellt werden. In .NET Framework 4.5 und höher können Datenvertragsklassen automatisch aus vorhandenen Diensten mit dem Contract-First-Tool erstellt werden. Zum Verwenden des Vertrag zuerst-Tools muss die XSD (XML Schema Definition)-Datei lokal heruntergeladen werden. Das Tool kann keine Remotedatenverträge per HTTP importieren.

 Das Contract-First-Tool wird als Buildaufgabe in Visual Studio 2012 integriert. Die von der Buildaufgabe generierten Codedateien werden bei jeder Projekterstellung erzeugt, sodass das Projekt einfach Änderungen im zugrunde liegenden Dienstvertrag übernehmen kann.

 Folgende Schematypen können vom Vertrag zuerst-Tool importiert werden:

```xml
<xsd:complexType>
 <xsd:simpleType>
 </xsd:simpleType>
</xsd:complexType>
```

 Einfache Typen werden nicht generiert, wenn es sich um primitive Typen, z. B. `Int16` oder `String`, handelt. Komplexe Typen werden nicht generiert, wenn sie vom Typ `Collection` sind. Typen werden ebenfalls nicht generiert, wenn sie Teil eines anderen `xsd:complexType` sind. In allen diesen Fällen werden stattdessen Verweise dieser Typen auf im Projekt vorhandene Typen verwendet.

## <a name="adding-a-data-contract-to-a-project"></a>Hinzufügen eines Datenvertrags zu einem Projekt
 Bevor das Vertrag zuerst-Tool verwendet werden kann, muss dem Projekt der Dienstvertrag (XSD) hinzugefügt werden. In dieser Übersicht wird zum Veranschaulichen von Vertrag zuerst-Funktionen der folgende Vertrag verwendet. Diese Dienstdefinition ist eine kleine Teilmenge des Dienstvertrags, der von der Bing-Suchapi verwendet wird.

```xml
<?xml version="1.0" encoding="utf-8"?>
<xs:schema id="ServiceSchema"
    targetNamespace="http://tempuri.org/ServiceSchema.xsd"
    elementFormDefault="qualified"
    xmlns="http://tempuri.org/ServiceSchema.xsd"
    xmlns:mstns="http://tempuri.org/ServiceSchema.xsd"
    xmlns:xs="http://www.w3.org/2001/XMLSchema"
>
  <xs:complexType name="SearchRequest">
    <xs:sequence>
      <xs:element minOccurs="0" maxOccurs="1" name="Version" type="xs:string" default="2.2" />
      <xs:element minOccurs="0" maxOccurs="1" name="Market" type="xs:string" />
      <xs:element minOccurs="0" maxOccurs="1" name="UILanguage" type="xs:string" />
      <xs:element minOccurs="1" maxOccurs="1" name="Query" type="xs:string" />
      <xs:element minOccurs="1" maxOccurs="1" name="AppId" type="xs:string" />
      <xs:element minOccurs="0" maxOccurs="1" name="Latitude" type="xs:double" />
      <xs:element minOccurs="0" maxOccurs="1" name="Longitude" type="xs:double" />
      <xs:element minOccurs="0" maxOccurs="1" name="Radius" type="xs:double" />
    </xs:sequence>
  </xs:complexType>
  <xs:simpleType name="WebSearchOption">
    <xs:restriction base="xs:string">
      <xs:enumeration value="DisableHostCollapsing" />
      <xs:enumeration value="DisableQueryAlterations" />
    </xs:restriction>
  </xs:simpleType>
</xs:schema>
```

 Um den oben genannten Servicevertrag zum Projekt hinzuzufügen, klicken Sie mit der rechten Maustaste auf das Projekt, und wählen Sie **Neu hinzufügen...**. Wählen Sie im WCF-Bereich des Dialogfelds Vorlagen die Schemadefinition aus, und benennen Sie die neue Datei mit SampleContract.xsd. Kopieren Sie den obigen Code, und fügen Sie ihn in die Codeansicht der neuen Datei ein.

## <a name="configuring-contract-first-options"></a>Konfigurieren von Vertrag zuerst-Optionen
 Vertragsoptionen können im Eigenschaftenmenü eines WCF-Projekts konfiguriert werden. Um die Erstentwicklung zu aktivieren, aktivieren Sie das Kontrollkästchen **XSD als Typdefinitionssprache aktivieren** auf der WCF-Seite des Projekteigenschaftenfensters.

 ![Screenshot der WCF-Optionen mit aktivierter Vertrags-First-Entwicklung.](./media/contract-first-tool/contract-first-options.png)

 Um erweiterte Eigenschaften zu konfigurieren, klicken Sie auf die Schaltfläche Erweitert.

 ![Dialogfeld erweiterte Vertragscodegenerierungseinstellungen.](./media/contract-first-tool/advanced-contract-settings.png)

 Die folgenden erweiterten Einstellungen können für die Codegenerierung aus Verträgen konfiguriert werden. Die Einstellungen können nur für alle Dateien im Projekt konfiguriert werden. Das Konfigurieren der Einstellungen für einzelne Dateien ist derzeit nicht möglich.

- **Serialisierungsmodus**: Diese Einstellung bestimmt, welcher Serialisierungsprogramm zum Lesen von Servicevertragsdateien verwendet wird. Wenn XML Serializer ausgewählt ist, werden die Optionen **Sammlungstypen** und **Wiederverwendungstypen** deaktiviert. **XML Serializer** Diese Optionen gelten nur für den **Data Contract Serializer**.

- **Wiederverwendungstypen**: Diese Einstellung gibt an, welche Bibliotheken für die Wiederverwendung vom Typ verwendet werden. Diese Einstellung gilt nur, wenn der **Serialisierungsmodus** auf **Data Contract Serializer**festgelegt ist.

- **Auflistungstyp**: Diese Einstellung gibt den vollqualifizierten oder Assembly-qualifizierten Typ an, der für den Auflistungsdatentyp verwendet werden soll. Diese Einstellung gilt nur, wenn der **Serialisierungsmodus** auf **Data Contract Serializer**festgelegt ist.

- **Wörterbuchtyp**: Diese Einstellung gibt den vollqualifizierten oder Assembly-qualifizierten Typ an, der für den Wörterbuchdatentyp verwendet werden soll.

- **EnableDataBinding**: Diese Einstellung gibt <xref:System.ComponentModel.INotifyPropertyChanged> an, ob die Schnittstelle für alle Datentypen implementiert werden soll, um die Datenbindung zu implementieren.

- **ExcludedTypes**:Diese Einstellung gibt die Liste der vollqualifizierten oder Assembly-qualifizierten Typen an, die von den assemblys ausgeschlossen werden sollen. Diese Einstellung gilt nur, wenn der **Serialisierungsmodus** auf **Data Contract Serializer**festgelegt ist.

- **GenerateInternalTypes**: Diese Einstellung gibt an, ob Klassen generiert werden sollen, die als intern markiert sind. Diese Einstellung gilt nur, wenn der **Serialisierungsmodus** auf **Data Contract Serializer**festgelegt ist.

- **GenerateSerializableTypes**: Diese Einstellung gibt an, <xref:System.SerializableAttribute> ob Klassen mit dem Attribut generiert werden sollen. Diese Einstellung gilt nur, wenn der **Serialisierungsmodus** auf **Data Contract Serializer**festgelegt ist.

- **ImportXMLTypes**: Diese Einstellung gibt an, ob der <xref:System.SerializableAttribute> Serialisierungsmodul <xref:System.Runtime.Serialization.DataContractAttribute> für Datenverträge so konfiguriert werden soll, dass das Attribut auf Klassen ohne attribut angewendet wird.  Diese Einstellung gilt nur, wenn der **Serialisierungsmodus** auf **Data Contract Serializer**festgelegt ist.

- **SupportFx35TypedDataSets**: Diese Einstellung gibt an, ob zusätzliche Funktionen für typisierte Datensätze bereitzustellen sind, die für .NET Framework 3.5 erstellt wurden. Wenn **der Serialisierungsmodus** auf XML <xref:System.Data.Design.TypedDataSetSchemaImporterExtensionFx35> **Serializer**festgelegt ist, wird die Erweiterung dem XML-Schemaimporter hinzugefügt, wenn dieser Wert auf True festgelegt ist. Wenn **der Serialisierungsmodus** auf Data Contract <xref:System.DateTimeOffset> **Serializer**festgelegt ist, wird der Typ von <xref:System.DateTimeOffset> den Verweisen ausgeschlossen, wenn dieser Wert auf False festgelegt ist, sodass immer ein für ältere Frameworkversionen generiert wird.

- **InputXsdFiles**: Diese Einstellung gibt die Liste der Eingabedateien an. Jede Datei muss ein gültiges XML-Schema enthalten.

- **Sprache**: Diese Einstellung gibt die Sprache des generierten Vertragscodes an. Die Einstellung muss vom <xref:System.CodeDom.Compiler.CodeDomProvider> erkannt werden können.

- **NamespaceMappings**: Diese Einstellung gibt die Zuordnungen aus den XSD-Zielnamespaces zu CLR-Namespaces an. Jede Zuordnung sollte folgendes Format aufweisen:

    ```xml
    "Schema Namespace, CLR Namespace"
    ```

     Die XML-Serialisierung akzeptiert nur eine Zuordnung im folgenden Format:

    ```xml
    "*, CLR Namespace"
    ```

- **OutputDirectory**: Diese Einstellung gibt das Verzeichnis an, in dem die Codedateien generiert werden.

 Die Einstellungen werden verwendet, um Dienstvertragstypen aus Vertragsdateien zu generieren, wenn das Projekt erstellt wird.

## <a name="using-contract-first-development"></a>Verwenden der Vertrag zuerst-Entwicklung
 Nachdem Sie dem Projekt den Servicevertrag hinzugefügt und die Buildeinstellungen bestätigt haben, erstellen Sie das Projekt, indem Sie **F6**drücken. Die Typen, die im Dienstvertrag definiert sind, stehen dann für die Verwendung im Projekt bereit.

 Um die im Dienstvertrag definierten Typen zu verwenden, fügen Sie unter dem aktuellen Namespace einen Verweis auf `ContractTypes` hinzu:

```csharp
using MyProjectNamespace.ContractTypes;
```

 Die im Servicevertrag definierten Typen können dann im Projekt aufgelöst werden, wie unten gezeigt:

 ![SearchRequest-Klasse wird in IntelliSense angezeigt, nachdem die ersten Buchstaben eingegeben wurden.](./media/contract-first-tool/service-contract-types.png)

 Die vom Tool generierten Typen werden in der Datei GeneratedXSDTypes.cs erstellt. Die Datei wird \<standardmäßig im Projektverzeichnis\<>/obj/ build configuration>/XSDGeneratedCode/ erstellt. Das Beispielschema am Anfang dieses Artikels wird wie folgt konvertiert:

```csharp
//------------------------------------------------------------------------------
// <auto-generated>
//     This code was generated by a tool.
//     Runtime Version:4.0.30319.17330
//
//     Changes to this file may cause incorrect behavior and will be lost if
//     the code is regenerated.
// </auto-generated>
//------------------------------------------------------------------------------

namespace TestXSD3.ContractTypes
{
    using System.Xml.Serialization;

    /// <remarks/>
    [System.CodeDom.Compiler.GeneratedCodeAttribute("System.Xml", "4.0.30319.17330")]
    [System.SerializableAttribute()]
    [System.Diagnostics.DebuggerStepThroughAttribute()]
    [System.ComponentModel.DesignerCategoryAttribute("code")]
    [System.Xml.Serialization.XmlTypeAttribute(Namespace="http://tempuri.org/ServiceSchema.xsd")]
    [System.Xml.Serialization.XmlRootAttribute(Namespace="http://tempuri.org/ServiceSchema.xsd", IsNullable=true)]
    public partial class SearchRequest
    {

        private string versionField;

        private string marketField;

        private string uILanguageField;

        private string queryField;

        private string appIdField;

        private double latitudeField;

        private bool latitudeFieldSpecified;

        private double longitudeField;

        private bool longitudeFieldSpecified;

        private double radiusField;

        private bool radiusFieldSpecified;

        public SearchRequest()
        {
            this.versionField = "2.2";
        }

        /// <remarks/>
        [System.ComponentModel.DefaultValueAttribute("2.2")]
        public string Version
        {
            get
            {
                return this.versionField;
            }
            set
            {
                this.versionField = value;
            }
        }

        /// <remarks/>
        public string Market
        {
            get
            {
                return this.marketField;
            }
            set
            {
                this.marketField = value;
            }
        }

        /// <remarks/>
        public string UILanguage
        {
            get
            {
                return this.uILanguageField;
            }
            set
            {
                this.uILanguageField = value;
            }
        }

        /// <remarks/>
        public string Query
        {
            get
            {
                return this.queryField;
            }
            set
            {
                this.queryField = value;
            }
        }

        /// <remarks/>
        public string AppId
        {
            get
            {
                return this.appIdField;
            }
            set
            {
                this.appIdField = value;
            }
        }

        /// <remarks/>
        public double Latitude
        {
            get
            {
                return this.latitudeField;
            }
            set
            {
                this.latitudeField = value;
            }
        }

        /// <remarks/>
        [System.Xml.Serialization.XmlIgnoreAttribute()]
        public bool LatitudeSpecified
        {
            get
            {
                return this.latitudeFieldSpecified;
            }
            set
            {
                this.latitudeFieldSpecified = value;
            }
        }

        /// <remarks/>
        public double Longitude
        {
            get
            {
                return this.longitudeField;
            }
            set
            {
                this.longitudeField = value;
            }
        }

        /// <remarks/>
        [System.Xml.Serialization.XmlIgnoreAttribute()]
        public bool LongitudeSpecified
        {
            get
            {
                return this.longitudeFieldSpecified;
            }
            set
            {
                this.longitudeFieldSpecified = value;
            }
        }

        /// <remarks/>
        public double Radius
        {
            get
            {
                return this.radiusField;
            }
            set
            {
                this.radiusField = value;
            }
        }

        /// <remarks/>
        [System.Xml.Serialization.XmlIgnoreAttribute()]
        public bool RadiusSpecified
        {
            get
            {
                return this.radiusFieldSpecified;
            }
            set
            {
                this.radiusFieldSpecified = value;
            }
        }
    }

    /// <remarks/>
    [System.CodeDom.Compiler.GeneratedCodeAttribute("System.Xml", "4.0.30319.17330")]
    [System.SerializableAttribute()]
    [System.Xml.Serialization.XmlTypeAttribute(Namespace="http://tempuri.org/ServiceSchema.xsd")]
    [System.Xml.Serialization.XmlRootAttribute(Namespace="http://tempuri.org/ServiceSchema.xsd", IsNullable=false)]
    public enum WebSearchOption
    {

        /// <remarks/>
        DisableHostCollapsing,

        /// <remarks/>
        DisableQueryAlterations,
    }
}
```

## <a name="errors-and-warnings"></a>Fehler und Warnungen
 Fehler und Warnungen, die bei der Analyse des XSD-Schemas auftreten, werden als Buildfehler und Warnungen angezeigt.

## <a name="interface-inheritance"></a>Schnittstellenvererbung
 Bei der Vertrag zuerst-Entwicklung kann keine Schnittstellenvererbung verwendet werden. Dies entspricht dem Verhalten von Schnittstellen in anderen Vorgängen. Verwenden Sie für eine Schnittstelle, die eine Basisschnittstelle erbt, zwei verschiedene Endpunkte. Der erste Endpunkt verwendet den geerbten Vertrag, und der zweite Endpunkt implementiert die Basisschnittstelle.
