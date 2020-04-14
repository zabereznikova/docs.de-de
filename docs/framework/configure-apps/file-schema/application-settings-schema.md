---
title: Anwendungseinstellungsschema
ms.date: 03/30/2017
helpviewer_keywords:
- schema application settings
- application settings, schema [Windows Forms]
- Windows Forms, application settings schema
- configuration schema [.NET Framework], application settings
ms.assetid: 5797fcff-6081-4e8c-bebf-63d9c70cf14b
ms.openlocfilehash: 90d471888950347c041b4824b659ce33fda512d7
ms.sourcegitcommit: 7980a91f90ae5eca859db7e6bfa03e23e76a1a50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/13/2020
ms.locfileid: "81242828"
---
# <a name="application-settings-schema"></a><span data-ttu-id="94662-102">Anwendungseinstellungsschema</span><span class="sxs-lookup"><span data-stu-id="94662-102">Application Settings schema</span></span>

<span data-ttu-id="94662-103">Mithilfe von Anwendungseinstellungen können eine Windows Forms- oder ASP.NET-Anwendung anwendungsbezogene und benutzerbezogene Einstellungen speichern und abrufen.</span><span class="sxs-lookup"><span data-stu-id="94662-103">Application settings allow a Windows Forms or ASP.NET application to store and retrieve application-scoped and user-scoped settings.</span></span> <span data-ttu-id="94662-104">In diesem Zusammenhang ist eine *Einstellung* alle Informationen, die spezifisch für die Anwendung oder spezifisch für den aktuellen Benutzer sein können – alles von einer Datenbankverbindungszeichenfolge bis zur bevorzugten Standardfenstergröße des Benutzers.</span><span class="sxs-lookup"><span data-stu-id="94662-104">In this context, a *setting* is any piece of information that may be specific to the application or specific to the current user — anything from a database connection string to the user's preferred default window size.</span></span>

<span data-ttu-id="94662-105">Standardmäßig verwenden Anwendungseinstellungen in einer Windows <xref:System.Configuration.LocalFileSettingsProvider> Forms-Anwendung die Klasse, die das .NET-Konfigurationssystem verwendet, um Einstellungen in einer XML-Konfigurationsdatei zu speichern.</span><span class="sxs-lookup"><span data-stu-id="94662-105">By default, application settings in a Windows Forms application uses the <xref:System.Configuration.LocalFileSettingsProvider> class, which uses the .NET configuration system to store settings in an XML configuration file.</span></span> <span data-ttu-id="94662-106">Weitere Informationen zu den Dateien, die von Anwendungseinstellungen verwendet werden, finden Sie unter [Architektur der Anwendungseinstellungen](../../winforms/advanced/application-settings-architecture.md).</span><span class="sxs-lookup"><span data-stu-id="94662-106">For more information about the files used by application settings, see [Application Settings Architecture](../../winforms/advanced/application-settings-architecture.md).</span></span>

<span data-ttu-id="94662-107">Die Anwendungseinstellungen definieren die folgenden Elemente als Teil der konfigurationsdateien, die sie verwendet.</span><span class="sxs-lookup"><span data-stu-id="94662-107">Application settings defines the following elements as part of the configuration files it uses.</span></span>

| <span data-ttu-id="94662-108">Element</span><span class="sxs-lookup"><span data-stu-id="94662-108">Element</span></span>                    | <span data-ttu-id="94662-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="94662-109">Description</span></span>                                                                           |
| -------------------------- | ------------------------------------------------------------------------------------- |
| <span data-ttu-id="94662-110">**\<applicationSettings>**</span><span class="sxs-lookup"><span data-stu-id="94662-110">**\<applicationSettings>**</span></span> | <span data-ttu-id="94662-111">Enthält \*\* \<\*\* alle Einstellungen>Tags, die für die Anwendung spezifisch sind.</span><span class="sxs-lookup"><span data-stu-id="94662-111">Contains all **\<setting>** tags specific to the application.</span></span>                         |
| <span data-ttu-id="94662-112">**\<userEinstellungen>**</span><span class="sxs-lookup"><span data-stu-id="94662-112">**\<userSettings>**</span></span>        | <span data-ttu-id="94662-113">Enthält \*\* \<\*\* alle Einstellungen>Tags, die für den aktuellen Benutzer spezifisch sind.</span><span class="sxs-lookup"><span data-stu-id="94662-113">Contains all **\<setting>** tags specific to the current user.</span></span>                        |
| <span data-ttu-id="94662-114">**\<Einstellung>**</span><span class="sxs-lookup"><span data-stu-id="94662-114">**\<setting>**</span></span>             | <span data-ttu-id="94662-115">Definiert eine Einstellung.</span><span class="sxs-lookup"><span data-stu-id="94662-115">Defines a setting.</span></span> <span data-ttu-id="94662-116">Untergeordnetes Element von \*\* \<applicationSettings>\*\* oder \*\* \<userSettings>\*\*.</span><span class="sxs-lookup"><span data-stu-id="94662-116">Child of either **\<applicationSettings>** or **\<userSettings>**.</span></span> |
| <span data-ttu-id="94662-117">**\<Wert>**</span><span class="sxs-lookup"><span data-stu-id="94662-117">**\<value>**</span></span>               | <span data-ttu-id="94662-118">Definiert den Wert einer Einstellung.</span><span class="sxs-lookup"><span data-stu-id="94662-118">Defines a setting's value.</span></span> <span data-ttu-id="94662-119">Kind \*\* \< \*\*der Einstellung>.</span><span class="sxs-lookup"><span data-stu-id="94662-119">Child of **\<setting>**.</span></span>                                   |

## <a name="applicationsettings-element"></a><span data-ttu-id="94662-120">\<applicationSettings>-Element</span><span class="sxs-lookup"><span data-stu-id="94662-120">\<applicationSettings> element</span></span>

<span data-ttu-id="94662-121">Dieses Element \*\* \<\*\* enthält alle Einstellungen>Tags, die für eine Instanz der Anwendung auf einem Clientcomputer spezifisch sind.</span><span class="sxs-lookup"><span data-stu-id="94662-121">This element contains all **\<setting>** tags that are specific to an instance of the application on a client computer.</span></span> <span data-ttu-id="94662-122">Es definiert keine Attribute.</span><span class="sxs-lookup"><span data-stu-id="94662-122">It defines no attributes.</span></span>

## <a name="usersettings-element"></a><span data-ttu-id="94662-123">\<userSettings>-Element</span><span class="sxs-lookup"><span data-stu-id="94662-123">\<userSettings> element</span></span>

<span data-ttu-id="94662-124">Dieses Element \*\* \<\*\* enthält alle Einstellungen>Tags, die für den Benutzer spezifisch sind, der die Anwendung derzeit verwendet.</span><span class="sxs-lookup"><span data-stu-id="94662-124">This element contains all **\<setting>** tags that are specific to the user who is currently using the application.</span></span> <span data-ttu-id="94662-125">Es definiert keine Attribute.</span><span class="sxs-lookup"><span data-stu-id="94662-125">It defines no attributes.</span></span>

## <a name="setting-element"></a><span data-ttu-id="94662-126">\<Festlegen> Elements</span><span class="sxs-lookup"><span data-stu-id="94662-126">\<setting> element</span></span>

<span data-ttu-id="94662-127">Dieses Element definiert eine Einstellung.</span><span class="sxs-lookup"><span data-stu-id="94662-127">This element defines a setting.</span></span> <span data-ttu-id="94662-128">Es hat die folgenden Attribute.</span><span class="sxs-lookup"><span data-stu-id="94662-128">It has the following attributes.</span></span>

| <span data-ttu-id="94662-129">Attribut</span><span class="sxs-lookup"><span data-stu-id="94662-129">Attribute</span></span>        | <span data-ttu-id="94662-130">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="94662-130">Description</span></span> |
| ---------------- | ----------- |
| <span data-ttu-id="94662-131">**name**</span><span class="sxs-lookup"><span data-stu-id="94662-131">**name**</span></span>         | <span data-ttu-id="94662-132">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="94662-132">Required.</span></span> <span data-ttu-id="94662-133">Die eindeutige ID der Einstellung.</span><span class="sxs-lookup"><span data-stu-id="94662-133">The unique ID of the setting.</span></span> <span data-ttu-id="94662-134">Einstellungen, die über Visual Studio `ProjectName.Properties.Settings`erstellt wurden, werden mit dem Namen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="94662-134">Settings created through Visual Studio are saved with the name `ProjectName.Properties.Settings`.</span></span> |
| <span data-ttu-id="94662-135">**Serializeas**</span><span class="sxs-lookup"><span data-stu-id="94662-135">**serializeAs**</span></span> | <span data-ttu-id="94662-136">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="94662-136">Required.</span></span> <span data-ttu-id="94662-137">Das Format, das zum Serialisieren des Werts in Text verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="94662-137">The format to use for serializing the value to text.</span></span> <span data-ttu-id="94662-138">Gültige Werte sind:</span><span class="sxs-lookup"><span data-stu-id="94662-138">Valid values are:</span></span><br><br><span data-ttu-id="94662-139">- `string`.</span><span class="sxs-lookup"><span data-stu-id="94662-139">- `string`.</span></span> <span data-ttu-id="94662-140">Der Wert wird als Zeichenfolge <xref:System.ComponentModel.TypeConverter>mit einer serialisiert.</span><span class="sxs-lookup"><span data-stu-id="94662-140">The value is serialized as a string using a <xref:System.ComponentModel.TypeConverter>.</span></span><br><span data-ttu-id="94662-141">- `xml`.</span><span class="sxs-lookup"><span data-stu-id="94662-141">- `xml`.</span></span> <span data-ttu-id="94662-142">Der Wert wird mithilfe der XML-Serialisierung serialisiert.</span><span class="sxs-lookup"><span data-stu-id="94662-142">The value is serialized using XML serialization.</span></span><br><span data-ttu-id="94662-143">- `binary`.</span><span class="sxs-lookup"><span data-stu-id="94662-143">- `binary`.</span></span> <span data-ttu-id="94662-144">Der Wert wird als textcodierte Binärdatei mithilfe der binären Serialisierung serialisiert.</span><span class="sxs-lookup"><span data-stu-id="94662-144">The value is serialized as text-encoded binary using binary serialization.</span></span><br /><span data-ttu-id="94662-145">- `custom`.</span><span class="sxs-lookup"><span data-stu-id="94662-145">- `custom`.</span></span> <span data-ttu-id="94662-146">Der Einstellungsanbieter verfügt über inhärente Kenntnisse dieser Einstellung und serialisiert und deserialisiert sie.</span><span class="sxs-lookup"><span data-stu-id="94662-146">The settings provider has inherent knowledge of this setting and serializes and de-serializes it.</span></span> |

## <a name="value-element"></a><span data-ttu-id="94662-147">\<Wert>-Element</span><span class="sxs-lookup"><span data-stu-id="94662-147">\<value> element</span></span>

<span data-ttu-id="94662-148">Dieses Element enthält den Wert einer Einstellung.</span><span class="sxs-lookup"><span data-stu-id="94662-148">This element contains the value of a setting.</span></span>

## <a name="example"></a><span data-ttu-id="94662-149">Beispiel</span><span class="sxs-lookup"><span data-stu-id="94662-149">Example</span></span>

<span data-ttu-id="94662-150">Das folgende Beispiel zeigt eine Anwendungseinstellungsdatei, die zwei anwendungsbezogene Und zwei benutzerbezogene Einstellungen definiert:</span><span class="sxs-lookup"><span data-stu-id="94662-150">The following example shows an application settings file that defines two application-scoped settings and two user-scoped settings:</span></span>

```xml
<?xml version="1.0" encoding="utf-8" ?>
<configuration>
  <configSections>
    <sectionGroup name="applicationSettings" type="System.Configuration.ApplicationSettingsGroup, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">
      <section name="WindowsApplication1.Properties.Settings" type="System.Configuration.ClientSettingsSection, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />
    </sectionGroup>
    <sectionGroup name="userSettings" type="System.Configuration.UserSettingsGroup, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">
      <section name="WindowsApplication1.Properties.Settings" type="System.Configuration.ClientSettingsSection, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" allowExeDefinition="MachineToLocalUser" />
    </sectionGroup>
  </configSections>
  <applicationSettings>
    <WindowsApplication1.Properties.Settings>
      <setting name="Cursor" serializeAs="String">
        <value>Default</value>
      </setting>
      <setting name="DoubleBuffering" serializeAs="String">
        <value>False</value>
      </setting>
    </WindowsApplication1.Properties.Settings>
  </applicationSettings>
  <userSettings>
    <WindowsApplication1.Properties.Settings>
      <setting name="FormTitle" serializeAs="String">
        <value>Form1</value>
      </setting>
      <setting name="FormSize" serializeAs="String">
        <value>595, 536</value>
      </setting>
    </WindowsApplication1.Properties.Settings>
  </userSettings>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="94662-151">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="94662-151">See also</span></span>

- [<span data-ttu-id="94662-152">Übersicht über Anwendungseinstellungen</span><span class="sxs-lookup"><span data-stu-id="94662-152">Application Settings Overview</span></span>](../../winforms/advanced/application-settings-overview.md)
- [<span data-ttu-id="94662-153">Architektur der Anwendungseinstellungen</span><span class="sxs-lookup"><span data-stu-id="94662-153">Application Settings Architecture</span></span>](../../winforms/advanced/application-settings-architecture.md)
