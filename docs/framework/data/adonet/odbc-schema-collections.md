---
title: ODBC-Schemaauflistungen
ms.date: 03/30/2017
ms.assetid: 1bb126a5-ceec-4649-a4bc-8aa19e801046
ms.openlocfilehash: bdedbb11960f02b99dcca6388abf663635238f74
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2018
ms.locfileid: "43877530"
---
# <a name="odbc-schema-collections"></a><span data-ttu-id="c497f-102">ODBC-Schemaauflistungen</span><span class="sxs-lookup"><span data-stu-id="c497f-102">ODBC Schema Collections</span></span>
<span data-ttu-id="c497f-103">In diesem Abschnitt wird die Unterstützung von Schemaauflistungen für die ODBC-Treiber für Microsoft SQL Server, Oracle und Microsoft Jet diskutiert.</span><span class="sxs-lookup"><span data-stu-id="c497f-103">This section discusses schema collection support for the ODBC drivers for Microsoft SQL Server, Oracle, and Microsoft Jet.</span></span>  
  
## <a name="microsoft-sql-server-odbc-driver"></a><span data-ttu-id="c497f-104">Microsoft SQL Server-ODBC-Treiber</span><span class="sxs-lookup"><span data-stu-id="c497f-104">Microsoft SQL Server ODBC Driver</span></span>  
 <span data-ttu-id="c497f-105">Der Microsoft SQL Server-ODBC-Treiber unterstützt neben den allgemeinen schemaauflistungen die folgenden spezifischen schemaauflistungen:</span><span class="sxs-lookup"><span data-stu-id="c497f-105">The Microsoft SQL Server ODBC Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="c497f-106">Tabellen</span><span class="sxs-lookup"><span data-stu-id="c497f-106">Tables</span></span>  
  
-   <span data-ttu-id="c497f-107">Indexes</span><span class="sxs-lookup"><span data-stu-id="c497f-107">Indexes</span></span>  
  
-   <span data-ttu-id="c497f-108">Columns</span><span class="sxs-lookup"><span data-stu-id="c497f-108">Columns</span></span>  
  
-   <span data-ttu-id="c497f-109">Verfahren</span><span class="sxs-lookup"><span data-stu-id="c497f-109">Procedures</span></span>  
  
-   <span data-ttu-id="c497f-110">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="c497f-110">ProcedureColumns</span></span>  
  
-   <span data-ttu-id="c497f-111">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="c497f-111">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="c497f-112">Ansichten</span><span class="sxs-lookup"><span data-stu-id="c497f-112">Views</span></span>  
  
### <a name="tables-and-views"></a><span data-ttu-id="c497f-113">Tables und Views</span><span class="sxs-lookup"><span data-stu-id="c497f-113">Tables and Views</span></span>  
  
|<span data-ttu-id="c497f-114">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="c497f-114">ColumnName</span></span>|<span data-ttu-id="c497f-115">DataType</span><span class="sxs-lookup"><span data-stu-id="c497f-115">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="c497f-116">TABLE_CAT</span><span class="sxs-lookup"><span data-stu-id="c497f-116">TABLE_CAT</span></span>|<span data-ttu-id="c497f-117">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="c497f-117">String</span></span>|  
|<span data-ttu-id="c497f-118">TABLE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="c497f-118">TABLE_SCHEM</span></span>|<span data-ttu-id="c497f-119">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="c497f-119">String</span></span>|  
|<span data-ttu-id="c497f-120">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="c497f-120">TABLE_NAME</span></span>|<span data-ttu-id="c497f-121">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="c497f-121">String</span></span>|  
|<span data-ttu-id="c497f-122">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="c497f-122">TABLE_TYPE</span></span>|<span data-ttu-id="c497f-123">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="c497f-123">String</span></span>|  
|<span data-ttu-id="c497f-124">REMARKS</span><span class="sxs-lookup"><span data-stu-id="c497f-124">REMARKS</span></span>|<span data-ttu-id="c497f-125">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="c497f-125">String</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="c497f-126">Indexes</span><span class="sxs-lookup"><span data-stu-id="c497f-126">Indexes</span></span>  
  
|<span data-ttu-id="c497f-127">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="c497f-127">ColumnName</span></span>|<span data-ttu-id="c497f-128">DataType</span><span class="sxs-lookup"><span data-stu-id="c497f-128">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="c497f-129">TABLE_CAT</span><span class="sxs-lookup"><span data-stu-id="c497f-129">TABLE_CAT</span></span>|<span data-ttu-id="c497f-130">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="c497f-130">String</span></span>|  
|<span data-ttu-id="c497f-131">TABLE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="c497f-131">TABLE_SCHEM</span></span>|<span data-ttu-id="c497f-132">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="c497f-132">String</span></span>|  
|<span data-ttu-id="c497f-133">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="c497f-133">TABLE_NAME</span></span>|<span data-ttu-id="c497f-134">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="c497f-134">String</span></span>|  
|<span data-ttu-id="c497f-135">NON_UNIQUE</span><span class="sxs-lookup"><span data-stu-id="c497f-135">NON_UNIQUE</span></span>|<span data-ttu-id="c497f-136">Int16</span><span class="sxs-lookup"><span data-stu-id="c497f-136">Int16</span></span>|  
|<span data-ttu-id="c497f-137">INDEX_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="c497f-137">INDEX_QUALIFIER</span></span>|<span data-ttu-id="c497f-138">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="c497f-138">String</span></span>|  
|<span data-ttu-id="c497f-139">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="c497f-139">INDEX_NAME</span></span>|<span data-ttu-id="c497f-140">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="c497f-140">String</span></span>|  
|<span data-ttu-id="c497f-141">TYPE</span><span class="sxs-lookup"><span data-stu-id="c497f-141">TYPE</span></span>|<span data-ttu-id="c497f-142">Int16</span><span class="sxs-lookup"><span data-stu-id="c497f-142">Int16</span></span>|  
|<span data-ttu-id="c497f-143">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="c497f-143">ORDINAL_POSITION</span></span>|<span data-ttu-id="c497f-144">Int16</span><span class="sxs-lookup"><span data-stu-id="c497f-144">Int16</span></span>|  
|<span data-ttu-id="c497f-145">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="c497f-145">COLUMN_NAME</span></span>|<span data-ttu-id="c497f-146">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="c497f-146">String</span></span>|  
|<span data-ttu-id="c497f-147">ASC_OR_DESC</span><span class="sxs-lookup"><span data-stu-id="c497f-147">ASC_OR_DESC</span></span>|<span data-ttu-id="c497f-148">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="c497f-148">String</span></span>|  
|<span data-ttu-id="c497f-149">CARDINATLITY</span><span class="sxs-lookup"><span data-stu-id="c497f-149">CARDINATLITY</span></span>|<span data-ttu-id="c497f-150">Int32</span><span class="sxs-lookup"><span data-stu-id="c497f-150">Int32</span></span>|  
|<span data-ttu-id="c497f-151">PAGES</span><span class="sxs-lookup"><span data-stu-id="c497f-151">PAGES</span></span>|<span data-ttu-id="c497f-152">Int32</span><span class="sxs-lookup"><span data-stu-id="c497f-152">Int32</span></span>|  
|<span data-ttu-id="c497f-153">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="c497f-153">FILTER_CONDITION</span></span>|<span data-ttu-id="c497f-154">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="c497f-154">String</span></span>|  
|<span data-ttu-id="c497f-155">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="c497f-155">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="c497f-156">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="c497f-156">String</span></span>|  
|<span data-ttu-id="c497f-157">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="c497f-157">SS_DATA_TYPE</span></span>|<span data-ttu-id="c497f-158">Byte</span><span class="sxs-lookup"><span data-stu-id="c497f-158">Byte</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="c497f-159">Columns</span><span class="sxs-lookup"><span data-stu-id="c497f-159">Columns</span></span>  
  
|<span data-ttu-id="c497f-160">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="c497f-160">ColumnName</span></span>|<span data-ttu-id="c497f-161">DataType</span><span class="sxs-lookup"><span data-stu-id="c497f-161">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="c497f-162">TABLE_CAT</span><span class="sxs-lookup"><span data-stu-id="c497f-162">TABLE_CAT</span></span>|<span data-ttu-id="c497f-163">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="c497f-163">String</span></span>|  
|<span data-ttu-id="c497f-164">TABLE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="c497f-164">TABLE_SCHEM</span></span>|<span data-ttu-id="c497f-165">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="c497f-165">String</span></span>|  
|<span data-ttu-id="c497f-166">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="c497f-166">TABLE_NAME</span></span>|<span data-ttu-id="c497f-167">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="c497f-167">String</span></span>|  
|<span data-ttu-id="c497f-168">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="c497f-168">COLUMN_NAME</span></span>|<span data-ttu-id="c497f-169">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="c497f-169">String</span></span>|  
|<span data-ttu-id="c497f-170">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="c497f-170">DATA_TYPE</span></span>|<span data-ttu-id="c497f-171">Int16</span><span class="sxs-lookup"><span data-stu-id="c497f-171">Int16</span></span>|  
|<span data-ttu-id="c497f-172">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="c497f-172">TYPE_NAME</span></span>|<span data-ttu-id="c497f-173">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="c497f-173">String</span></span>|  
|<span data-ttu-id="c497f-174">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="c497f-174">COLUMN_SIZE</span></span>|<span data-ttu-id="c497f-175">Int32</span><span class="sxs-lookup"><span data-stu-id="c497f-175">Int32</span></span>|  
|<span data-ttu-id="c497f-176">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="c497f-176">BUFFER_LENGTH</span></span>|<span data-ttu-id="c497f-177">Int32</span><span class="sxs-lookup"><span data-stu-id="c497f-177">Int32</span></span>|  
|<span data-ttu-id="c497f-178">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="c497f-178">DECIMAL_DIGITS</span></span>|<span data-ttu-id="c497f-179">Int16</span><span class="sxs-lookup"><span data-stu-id="c497f-179">Int16</span></span>|  
|<span data-ttu-id="c497f-180">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="c497f-180">NUM_PREC_RADIX</span></span>|<span data-ttu-id="c497f-181">Int16</span><span class="sxs-lookup"><span data-stu-id="c497f-181">Int16</span></span>|  
|<span data-ttu-id="c497f-182">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="c497f-182">NULLABLE</span></span>|<span data-ttu-id="c497f-183">Int16</span><span class="sxs-lookup"><span data-stu-id="c497f-183">Int16</span></span>|  
|<span data-ttu-id="c497f-184">REMARKS</span><span class="sxs-lookup"><span data-stu-id="c497f-184">REMARKS</span></span>|<span data-ttu-id="c497f-185">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="c497f-185">String</span></span>|  
|<span data-ttu-id="c497f-186">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="c497f-186">COLUMN_DEF</span></span>|<span data-ttu-id="c497f-187">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="c497f-187">String</span></span>|  
|<span data-ttu-id="c497f-188">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="c497f-188">SQL_DATA_TYPE</span></span>|<span data-ttu-id="c497f-189">Int16</span><span class="sxs-lookup"><span data-stu-id="c497f-189">Int16</span></span>|  
|<span data-ttu-id="c497f-190">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="c497f-190">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="c497f-191">Int16</span><span class="sxs-lookup"><span data-stu-id="c497f-191">Int16</span></span>|  
|<span data-ttu-id="c497f-192">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="c497f-192">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="c497f-193">Int32</span><span class="sxs-lookup"><span data-stu-id="c497f-193">Int32</span></span>|  
|<span data-ttu-id="c497f-194">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="c497f-194">ORDINAL_POSITION</span></span>|<span data-ttu-id="c497f-195">Int32</span><span class="sxs-lookup"><span data-stu-id="c497f-195">Int32</span></span>|  
|<span data-ttu-id="c497f-196">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="c497f-196">IS_NULLABLE</span></span>|<span data-ttu-id="c497f-197">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="c497f-197">String</span></span>|  
|<span data-ttu-id="c497f-198">SS_TYPE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="c497f-198">SS_TYPE_CATALOG</span></span>|<span data-ttu-id="c497f-199">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="c497f-199">String</span></span>|  
|<span data-ttu-id="c497f-200">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="c497f-200">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="c497f-201">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="c497f-201">String</span></span>|  
|<span data-ttu-id="c497f-202">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="c497f-202">SS_DATA_TYPE</span></span>|<span data-ttu-id="c497f-203">Byte</span><span class="sxs-lookup"><span data-stu-id="c497f-203">Byte</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="c497f-204">Verfahren</span><span class="sxs-lookup"><span data-stu-id="c497f-204">Procedures</span></span>  
  
|<span data-ttu-id="c497f-205">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="c497f-205">ColumnName</span></span>|<span data-ttu-id="c497f-206">DataType</span><span class="sxs-lookup"><span data-stu-id="c497f-206">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="c497f-207">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="c497f-207">PROCEDURE_CAT</span></span>|<span data-ttu-id="c497f-208">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="c497f-208">String</span></span>|  
|<span data-ttu-id="c497f-209">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="c497f-209">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="c497f-210">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="c497f-210">String</span></span>|  
|<span data-ttu-id="c497f-211">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="c497f-211">PROCEDURE_NAME</span></span>|<span data-ttu-id="c497f-212">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="c497f-212">String</span></span>|  
|<span data-ttu-id="c497f-213">NUM_INPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="c497f-213">NUM_INPUT_PARAMS</span></span>|<span data-ttu-id="c497f-214">Int32</span><span class="sxs-lookup"><span data-stu-id="c497f-214">Int32</span></span>|  
|<span data-ttu-id="c497f-215">NUM_OUTPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="c497f-215">NUM_OUTPUT_PARAMS</span></span>|<span data-ttu-id="c497f-216">Int32</span><span class="sxs-lookup"><span data-stu-id="c497f-216">Int32</span></span>|  
|<span data-ttu-id="c497f-217">NUM_RESULT_SETS</span><span class="sxs-lookup"><span data-stu-id="c497f-217">NUM_RESULT_SETS</span></span>|<span data-ttu-id="c497f-218">Int32</span><span class="sxs-lookup"><span data-stu-id="c497f-218">Int32</span></span>|  
|<span data-ttu-id="c497f-219">REMARKS</span><span class="sxs-lookup"><span data-stu-id="c497f-219">REMARKS</span></span>|<span data-ttu-id="c497f-220">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="c497f-220">String</span></span>|  
|<span data-ttu-id="c497f-221">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="c497f-221">PROCEDURE_TYPE</span></span>|<span data-ttu-id="c497f-222">Int16</span><span class="sxs-lookup"><span data-stu-id="c497f-222">Int16</span></span>|  
  
### <a name="procedurecolumns"></a><span data-ttu-id="c497f-223">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="c497f-223">ProcedureColumns</span></span>  
  
|<span data-ttu-id="c497f-224">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="c497f-224">ColumnName</span></span>|<span data-ttu-id="c497f-225">DataType</span><span class="sxs-lookup"><span data-stu-id="c497f-225">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="c497f-226">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="c497f-226">PROCEDURE_CAT</span></span>|<span data-ttu-id="c497f-227">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="c497f-227">String</span></span>|  
|<span data-ttu-id="c497f-228">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="c497f-228">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="c497f-229">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="c497f-229">String</span></span>|  
|<span data-ttu-id="c497f-230">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="c497f-230">PROCEDURE_NAME</span></span>|<span data-ttu-id="c497f-231">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="c497f-231">String</span></span>|  
|<span data-ttu-id="c497f-232">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="c497f-232">COLUMN_NAME</span></span>|<span data-ttu-id="c497f-233">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="c497f-233">String</span></span>|  
|<span data-ttu-id="c497f-234">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="c497f-234">COLUMN_TYPE</span></span>|<span data-ttu-id="c497f-235">Int16</span><span class="sxs-lookup"><span data-stu-id="c497f-235">Int16</span></span>|  
|<span data-ttu-id="c497f-236">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="c497f-236">DATA_TYPE</span></span>|<span data-ttu-id="c497f-237">Int16</span><span class="sxs-lookup"><span data-stu-id="c497f-237">Int16</span></span>|  
|<span data-ttu-id="c497f-238">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="c497f-238">TYPE_NAME</span></span>|<span data-ttu-id="c497f-239">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="c497f-239">String</span></span>|  
|<span data-ttu-id="c497f-240">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="c497f-240">COLUMN_SIZE</span></span>|<span data-ttu-id="c497f-241">Int32</span><span class="sxs-lookup"><span data-stu-id="c497f-241">Int32</span></span>|  
|<span data-ttu-id="c497f-242">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="c497f-242">BUFFER_LENGTH</span></span>|<span data-ttu-id="c497f-243">Int32</span><span class="sxs-lookup"><span data-stu-id="c497f-243">Int32</span></span>|  
|<span data-ttu-id="c497f-244">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="c497f-244">DECIMAL_DIGITS</span></span>|<span data-ttu-id="c497f-245">Int16</span><span class="sxs-lookup"><span data-stu-id="c497f-245">Int16</span></span>|  
|<span data-ttu-id="c497f-246">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="c497f-246">NUM_PREC_RADIX</span></span>|<span data-ttu-id="c497f-247">Int16</span><span class="sxs-lookup"><span data-stu-id="c497f-247">Int16</span></span>|  
|<span data-ttu-id="c497f-248">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="c497f-248">NULLABLE</span></span>|<span data-ttu-id="c497f-249">Int16</span><span class="sxs-lookup"><span data-stu-id="c497f-249">Int16</span></span>|  
|<span data-ttu-id="c497f-250">REMARKS</span><span class="sxs-lookup"><span data-stu-id="c497f-250">REMARKS</span></span>|<span data-ttu-id="c497f-251">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="c497f-251">String</span></span>|  
|<span data-ttu-id="c497f-252">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="c497f-252">COLUMN_DEF</span></span>|<span data-ttu-id="c497f-253">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="c497f-253">String</span></span>|  
|<span data-ttu-id="c497f-254">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="c497f-254">SQL_DATA_TYPE</span></span>|<span data-ttu-id="c497f-255">Int16</span><span class="sxs-lookup"><span data-stu-id="c497f-255">Int16</span></span>|  
|<span data-ttu-id="c497f-256">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="c497f-256">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="c497f-257">Int16</span><span class="sxs-lookup"><span data-stu-id="c497f-257">Int16</span></span>|  
|<span data-ttu-id="c497f-258">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="c497f-258">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="c497f-259">Int32</span><span class="sxs-lookup"><span data-stu-id="c497f-259">Int32</span></span>|  
|<span data-ttu-id="c497f-260">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="c497f-260">ORDINAL_POSITION</span></span>|<span data-ttu-id="c497f-261">Int32</span><span class="sxs-lookup"><span data-stu-id="c497f-261">Int32</span></span>|  
|<span data-ttu-id="c497f-262">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="c497f-262">IS_NULLABLE</span></span>|<span data-ttu-id="c497f-263">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="c497f-263">String</span></span>|  
|<span data-ttu-id="c497f-264">SS_TYPE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="c497f-264">SS_TYPE_CATALOG</span></span>|<span data-ttu-id="c497f-265">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="c497f-265">String</span></span>|  
|<span data-ttu-id="c497f-266">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="c497f-266">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="c497f-267">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="c497f-267">String</span></span>|  
|<span data-ttu-id="c497f-268">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="c497f-268">SS_DATA_TYPE</span></span>|<span data-ttu-id="c497f-269">Byte</span><span class="sxs-lookup"><span data-stu-id="c497f-269">Byte</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="c497f-270">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="c497f-270">ProcedureParameters</span></span>  
  
|<span data-ttu-id="c497f-271">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="c497f-271">ColumnName</span></span>|<span data-ttu-id="c497f-272">DataType</span><span class="sxs-lookup"><span data-stu-id="c497f-272">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="c497f-273">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="c497f-273">PROCEDURE_CAT</span></span>|<span data-ttu-id="c497f-274">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="c497f-274">String</span></span>|  
|<span data-ttu-id="c497f-275">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="c497f-275">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="c497f-276">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="c497f-276">String</span></span>|  
|<span data-ttu-id="c497f-277">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="c497f-277">PROCEDURE_NAME</span></span>|<span data-ttu-id="c497f-278">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="c497f-278">String</span></span>|  
|<span data-ttu-id="c497f-279">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="c497f-279">COLUMN_NAME</span></span>|<span data-ttu-id="c497f-280">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="c497f-280">String</span></span>|  
|<span data-ttu-id="c497f-281">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="c497f-281">COLUMN_TYPE</span></span>|<span data-ttu-id="c497f-282">Int16</span><span class="sxs-lookup"><span data-stu-id="c497f-282">Int16</span></span>|  
|<span data-ttu-id="c497f-283">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="c497f-283">DATA_TYPE</span></span>|<span data-ttu-id="c497f-284">Int16</span><span class="sxs-lookup"><span data-stu-id="c497f-284">Int16</span></span>|  
|<span data-ttu-id="c497f-285">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="c497f-285">TYPE_NAME</span></span>|<span data-ttu-id="c497f-286">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="c497f-286">String</span></span>|  
|<span data-ttu-id="c497f-287">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="c497f-287">COLUMN_SIZE</span></span>|<span data-ttu-id="c497f-288">Int32</span><span class="sxs-lookup"><span data-stu-id="c497f-288">Int32</span></span>|  
|<span data-ttu-id="c497f-289">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="c497f-289">BUFFER_LENGTH</span></span>|<span data-ttu-id="c497f-290">Int32</span><span class="sxs-lookup"><span data-stu-id="c497f-290">Int32</span></span>|  
|<span data-ttu-id="c497f-291">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="c497f-291">DECIMAL_DIGITS</span></span>|<span data-ttu-id="c497f-292">Int16</span><span class="sxs-lookup"><span data-stu-id="c497f-292">Int16</span></span>|  
|<span data-ttu-id="c497f-293">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="c497f-293">NUM_PREC_RADIX</span></span>|<span data-ttu-id="c497f-294">Int16</span><span class="sxs-lookup"><span data-stu-id="c497f-294">Int16</span></span>|  
|<span data-ttu-id="c497f-295">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="c497f-295">NULLABLE</span></span>|<span data-ttu-id="c497f-296">Int16</span><span class="sxs-lookup"><span data-stu-id="c497f-296">Int16</span></span>|  
|<span data-ttu-id="c497f-297">REMARKS</span><span class="sxs-lookup"><span data-stu-id="c497f-297">REMARKS</span></span>|<span data-ttu-id="c497f-298">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="c497f-298">String</span></span>|  
|<span data-ttu-id="c497f-299">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="c497f-299">COLUMN_DEF</span></span>|<span data-ttu-id="c497f-300">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="c497f-300">String</span></span>|  
|<span data-ttu-id="c497f-301">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="c497f-301">SQL_DATA_TYPE</span></span>|<span data-ttu-id="c497f-302">Int16</span><span class="sxs-lookup"><span data-stu-id="c497f-302">Int16</span></span>|  
|<span data-ttu-id="c497f-303">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="c497f-303">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="c497f-304">Int16</span><span class="sxs-lookup"><span data-stu-id="c497f-304">Int16</span></span>|  
|<span data-ttu-id="c497f-305">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="c497f-305">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="c497f-306">Int32</span><span class="sxs-lookup"><span data-stu-id="c497f-306">Int32</span></span>|  
|<span data-ttu-id="c497f-307">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="c497f-307">ORDINAL_POSITION</span></span>|<span data-ttu-id="c497f-308">Int32</span><span class="sxs-lookup"><span data-stu-id="c497f-308">Int32</span></span>|  
|<span data-ttu-id="c497f-309">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="c497f-309">IS_NULLABLE</span></span>|<span data-ttu-id="c497f-310">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="c497f-310">String</span></span>|  
|<span data-ttu-id="c497f-311">SS_TYPE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="c497f-311">SS_TYPE_CATALOG</span></span>|<span data-ttu-id="c497f-312">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="c497f-312">String</span></span>|  
|<span data-ttu-id="c497f-313">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="c497f-313">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="c497f-314">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="c497f-314">String</span></span>|  
|<span data-ttu-id="c497f-315">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="c497f-315">SS_DATA_TYPE</span></span>|<span data-ttu-id="c497f-316">Byte</span><span class="sxs-lookup"><span data-stu-id="c497f-316">Byte</span></span>|  
  
## <a name="microsoft-oracle-odbc-driver"></a><span data-ttu-id="c497f-317">Microsoft Oracle ODBC-Treiber</span><span class="sxs-lookup"><span data-stu-id="c497f-317">Microsoft Oracle ODBC Driver</span></span>  
 <span data-ttu-id="c497f-318">Der Microsoft SQL Server Oracle ODBC-Treiber unterstützt neben den allgemeinen schemaauflistungen die folgenden spezifischen schemaauflistungen:</span><span class="sxs-lookup"><span data-stu-id="c497f-318">The Microsoft SQL Server Oracle ODBC Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="c497f-319">Tabellen</span><span class="sxs-lookup"><span data-stu-id="c497f-319">Tables</span></span>  
  
-   <span data-ttu-id="c497f-320">Columns</span><span class="sxs-lookup"><span data-stu-id="c497f-320">Columns</span></span>  
  
-   <span data-ttu-id="c497f-321">Verfahren</span><span class="sxs-lookup"><span data-stu-id="c497f-321">Procedures</span></span>  
  
-   <span data-ttu-id="c497f-322">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="c497f-322">ProcedureColumns</span></span>  
  
-   <span data-ttu-id="c497f-323">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="c497f-323">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="c497f-324">Ansichten</span><span class="sxs-lookup"><span data-stu-id="c497f-324">Views</span></span>  
  
-   <span data-ttu-id="c497f-325">Indexes</span><span class="sxs-lookup"><span data-stu-id="c497f-325">Indexes</span></span>  
  
### <a name="tables-and-views"></a><span data-ttu-id="c497f-326">Tables und Views</span><span class="sxs-lookup"><span data-stu-id="c497f-326">Tables and Views</span></span>  
  
|<span data-ttu-id="c497f-327">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="c497f-327">ColumnName</span></span>|<span data-ttu-id="c497f-328">DataType</span><span class="sxs-lookup"><span data-stu-id="c497f-328">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="c497f-329">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="c497f-329">TABLE_QUALIFIER</span></span>|<span data-ttu-id="c497f-330">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="c497f-330">String</span></span>|  
|<span data-ttu-id="c497f-331">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="c497f-331">TABLE_OWNER</span></span>|<span data-ttu-id="c497f-332">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="c497f-332">String</span></span>|  
|<span data-ttu-id="c497f-333">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="c497f-333">TABLE_NAME</span></span>|<span data-ttu-id="c497f-334">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="c497f-334">String</span></span>|  
|<span data-ttu-id="c497f-335">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="c497f-335">TABLE_TYPE</span></span>|<span data-ttu-id="c497f-336">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="c497f-336">String</span></span>|  
|<span data-ttu-id="c497f-337">REMARKS</span><span class="sxs-lookup"><span data-stu-id="c497f-337">REMARKS</span></span>|<span data-ttu-id="c497f-338">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="c497f-338">String</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="c497f-339">Columns</span><span class="sxs-lookup"><span data-stu-id="c497f-339">Columns</span></span>  
  
|<span data-ttu-id="c497f-340">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="c497f-340">ColumnName</span></span>|<span data-ttu-id="c497f-341">DataType</span><span class="sxs-lookup"><span data-stu-id="c497f-341">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="c497f-342">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="c497f-342">TABLE_QUALIFIER</span></span>|<span data-ttu-id="c497f-343">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="c497f-343">String</span></span>|  
|<span data-ttu-id="c497f-344">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="c497f-344">TABLE_OWNER</span></span>|<span data-ttu-id="c497f-345">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="c497f-345">String</span></span>|  
|<span data-ttu-id="c497f-346">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="c497f-346">TABLE_NAME</span></span>|<span data-ttu-id="c497f-347">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="c497f-347">String</span></span>|  
|<span data-ttu-id="c497f-348">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="c497f-348">COLUMN_NAME</span></span>|<span data-ttu-id="c497f-349">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="c497f-349">String</span></span>|  
|<span data-ttu-id="c497f-350">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="c497f-350">DATA_TYPE</span></span>|<span data-ttu-id="c497f-351">Int16</span><span class="sxs-lookup"><span data-stu-id="c497f-351">Int16</span></span>|  
|<span data-ttu-id="c497f-352">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="c497f-352">TYPE_NAME</span></span>|<span data-ttu-id="c497f-353">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="c497f-353">String</span></span>|  
|<span data-ttu-id="c497f-354">PRECISION</span><span class="sxs-lookup"><span data-stu-id="c497f-354">PRECISION</span></span>|<span data-ttu-id="c497f-355">Int32</span><span class="sxs-lookup"><span data-stu-id="c497f-355">Int32</span></span>|  
|<span data-ttu-id="c497f-356">LENGTH</span><span class="sxs-lookup"><span data-stu-id="c497f-356">LENGTH</span></span>|<span data-ttu-id="c497f-357">Int32</span><span class="sxs-lookup"><span data-stu-id="c497f-357">Int32</span></span>|  
|<span data-ttu-id="c497f-358">SCALE</span><span class="sxs-lookup"><span data-stu-id="c497f-358">SCALE</span></span>|<span data-ttu-id="c497f-359">Int16</span><span class="sxs-lookup"><span data-stu-id="c497f-359">Int16</span></span>|  
|<span data-ttu-id="c497f-360">RADIX</span><span class="sxs-lookup"><span data-stu-id="c497f-360">RADIX</span></span>|<span data-ttu-id="c497f-361">Int16</span><span class="sxs-lookup"><span data-stu-id="c497f-361">Int16</span></span>|  
|<span data-ttu-id="c497f-362">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="c497f-362">NULLABLE</span></span>|<span data-ttu-id="c497f-363">Int16</span><span class="sxs-lookup"><span data-stu-id="c497f-363">Int16</span></span>|  
|<span data-ttu-id="c497f-364">REMARKS</span><span class="sxs-lookup"><span data-stu-id="c497f-364">REMARKS</span></span>|<span data-ttu-id="c497f-365">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="c497f-365">String</span></span>|  
|<span data-ttu-id="c497f-366">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="c497f-366">ORDINAL_POSITION</span></span>|<span data-ttu-id="c497f-367">Int32</span><span class="sxs-lookup"><span data-stu-id="c497f-367">Int32</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="c497f-368">Verfahren</span><span class="sxs-lookup"><span data-stu-id="c497f-368">Procedures</span></span>  
  
|<span data-ttu-id="c497f-369">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="c497f-369">ColumnName</span></span>|<span data-ttu-id="c497f-370">DataType</span><span class="sxs-lookup"><span data-stu-id="c497f-370">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="c497f-371">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="c497f-371">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="c497f-372">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="c497f-372">String</span></span>|  
|<span data-ttu-id="c497f-373">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="c497f-373">PROCEDURE_OWNER</span></span>|<span data-ttu-id="c497f-374">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="c497f-374">String</span></span>|  
|<span data-ttu-id="c497f-375">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="c497f-375">PROCEDURE_NAME</span></span>|<span data-ttu-id="c497f-376">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="c497f-376">String</span></span>|  
|<span data-ttu-id="c497f-377">NUM_INPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="c497f-377">NUM_INPUT_PARAMS</span></span>|<span data-ttu-id="c497f-378">Int16</span><span class="sxs-lookup"><span data-stu-id="c497f-378">Int16</span></span>|  
|<span data-ttu-id="c497f-379">NUM_OUTPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="c497f-379">NUM_OUTPUT_PARAMS</span></span>|<span data-ttu-id="c497f-380">Int16</span><span class="sxs-lookup"><span data-stu-id="c497f-380">Int16</span></span>|  
|<span data-ttu-id="c497f-381">NUM_RESULT_SETS</span><span class="sxs-lookup"><span data-stu-id="c497f-381">NUM_RESULT_SETS</span></span>|<span data-ttu-id="c497f-382">Int16</span><span class="sxs-lookup"><span data-stu-id="c497f-382">Int16</span></span>|  
|<span data-ttu-id="c497f-383">REMARKS</span><span class="sxs-lookup"><span data-stu-id="c497f-383">REMARKS</span></span>|<span data-ttu-id="c497f-384">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="c497f-384">String</span></span>|  
|<span data-ttu-id="c497f-385">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="c497f-385">PROCEDURE_TYPE</span></span>|<span data-ttu-id="c497f-386">Int16</span><span class="sxs-lookup"><span data-stu-id="c497f-386">Int16</span></span>|  
  
### <a name="procedurecolumns"></a><span data-ttu-id="c497f-387">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="c497f-387">ProcedureColumns</span></span>  
  
|<span data-ttu-id="c497f-388">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="c497f-388">ColumnName</span></span>|<span data-ttu-id="c497f-389">DataType</span><span class="sxs-lookup"><span data-stu-id="c497f-389">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="c497f-390">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="c497f-390">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="c497f-391">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="c497f-391">String</span></span>|  
|<span data-ttu-id="c497f-392">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="c497f-392">PROCEDURE_OWNER</span></span>|<span data-ttu-id="c497f-393">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="c497f-393">String</span></span>|  
|<span data-ttu-id="c497f-394">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="c497f-394">PROCEDURE_NAME</span></span>|<span data-ttu-id="c497f-395">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="c497f-395">String</span></span>|  
|<span data-ttu-id="c497f-396">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="c497f-396">COLUMN_NAME</span></span>|<span data-ttu-id="c497f-397">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="c497f-397">String</span></span>|  
|<span data-ttu-id="c497f-398">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="c497f-398">COLUMN_TYPE</span></span>|<span data-ttu-id="c497f-399">Int16</span><span class="sxs-lookup"><span data-stu-id="c497f-399">Int16</span></span>|  
|<span data-ttu-id="c497f-400">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="c497f-400">DATA_TYPE</span></span>|<span data-ttu-id="c497f-401">Int16</span><span class="sxs-lookup"><span data-stu-id="c497f-401">Int16</span></span>|  
|<span data-ttu-id="c497f-402">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="c497f-402">TYPE_NAME</span></span>|<span data-ttu-id="c497f-403">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="c497f-403">String</span></span>|  
|<span data-ttu-id="c497f-404">PRECISION</span><span class="sxs-lookup"><span data-stu-id="c497f-404">PRECISION</span></span>|<span data-ttu-id="c497f-405">Int32</span><span class="sxs-lookup"><span data-stu-id="c497f-405">Int32</span></span>|  
|<span data-ttu-id="c497f-406">LENGTH</span><span class="sxs-lookup"><span data-stu-id="c497f-406">LENGTH</span></span>|<span data-ttu-id="c497f-407">Int32</span><span class="sxs-lookup"><span data-stu-id="c497f-407">Int32</span></span>|  
|<span data-ttu-id="c497f-408">SCALE</span><span class="sxs-lookup"><span data-stu-id="c497f-408">SCALE</span></span>|<span data-ttu-id="c497f-409">Int16</span><span class="sxs-lookup"><span data-stu-id="c497f-409">Int16</span></span>|  
|<span data-ttu-id="c497f-410">RADIX</span><span class="sxs-lookup"><span data-stu-id="c497f-410">RADIX</span></span>|<span data-ttu-id="c497f-411">Int16</span><span class="sxs-lookup"><span data-stu-id="c497f-411">Int16</span></span>|  
|<span data-ttu-id="c497f-412">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="c497f-412">NULLABLE</span></span>|<span data-ttu-id="c497f-413">Int16</span><span class="sxs-lookup"><span data-stu-id="c497f-413">Int16</span></span>|  
|<span data-ttu-id="c497f-414">REMARKS</span><span class="sxs-lookup"><span data-stu-id="c497f-414">REMARKS</span></span>|<span data-ttu-id="c497f-415">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="c497f-415">String</span></span>|  
|<span data-ttu-id="c497f-416">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="c497f-416">OVERLOAD</span></span>|<span data-ttu-id="c497f-417">Int32</span><span class="sxs-lookup"><span data-stu-id="c497f-417">Int32</span></span>|  
|<span data-ttu-id="c497f-418">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="c497f-418">ORDINAL_POSITION</span></span>|<span data-ttu-id="c497f-419">Int32</span><span class="sxs-lookup"><span data-stu-id="c497f-419">Int32</span></span>|  
  
## <a name="microsoft-jet-odbc-driver"></a><span data-ttu-id="c497f-420">Microsoft Jet ODBC-Treiber</span><span class="sxs-lookup"><span data-stu-id="c497f-420">Microsoft Jet ODBC Driver</span></span>  
 <span data-ttu-id="c497f-421">Der Microsoft Jet ODBC-Treiber unterstützt neben den allgemeinen Schemaauflistungen auch die folgenden spezifischen Schemaauflistungen:</span><span class="sxs-lookup"><span data-stu-id="c497f-421">The Microsoft Jet ODBC Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="c497f-422">Tabellen</span><span class="sxs-lookup"><span data-stu-id="c497f-422">Tables</span></span>  
  
-   <span data-ttu-id="c497f-423">Indexes</span><span class="sxs-lookup"><span data-stu-id="c497f-423">Indexes</span></span>  
  
-   <span data-ttu-id="c497f-424">Columns</span><span class="sxs-lookup"><span data-stu-id="c497f-424">Columns</span></span>  
  
-   <span data-ttu-id="c497f-425">Verfahren</span><span class="sxs-lookup"><span data-stu-id="c497f-425">Procedures</span></span>  
  
-   <span data-ttu-id="c497f-426">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="c497f-426">ProcedureColumns</span></span>  
  
-   <span data-ttu-id="c497f-427">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="c497f-427">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="c497f-428">Ansichten</span><span class="sxs-lookup"><span data-stu-id="c497f-428">Views</span></span>  
  
### <a name="tables-and-views"></a><span data-ttu-id="c497f-429">Tables und Views</span><span class="sxs-lookup"><span data-stu-id="c497f-429">Tables and Views</span></span>  
  
|<span data-ttu-id="c497f-430">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="c497f-430">ColumnName</span></span>|<span data-ttu-id="c497f-431">DataType</span><span class="sxs-lookup"><span data-stu-id="c497f-431">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="c497f-432">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="c497f-432">TABLE_QUALIFIER</span></span>|<span data-ttu-id="c497f-433">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="c497f-433">String</span></span>|  
|<span data-ttu-id="c497f-434">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="c497f-434">TABLE_OWNER</span></span>|<span data-ttu-id="c497f-435">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="c497f-435">String</span></span>|  
|<span data-ttu-id="c497f-436">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="c497f-436">TABLE_NAME</span></span>|<span data-ttu-id="c497f-437">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="c497f-437">String</span></span>|  
|<span data-ttu-id="c497f-438">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="c497f-438">TABLE_TYPE</span></span>|<span data-ttu-id="c497f-439">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="c497f-439">String</span></span>|  
|<span data-ttu-id="c497f-440">REMARKS</span><span class="sxs-lookup"><span data-stu-id="c497f-440">REMARKS</span></span>|<span data-ttu-id="c497f-441">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="c497f-441">String</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="c497f-442">Columns</span><span class="sxs-lookup"><span data-stu-id="c497f-442">Columns</span></span>  
  
|<span data-ttu-id="c497f-443">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="c497f-443">ColumnName</span></span>|<span data-ttu-id="c497f-444">DataType</span><span class="sxs-lookup"><span data-stu-id="c497f-444">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="c497f-445">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="c497f-445">TABLE_QUALIFIER</span></span>|<span data-ttu-id="c497f-446">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="c497f-446">String</span></span>|  
|<span data-ttu-id="c497f-447">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="c497f-447">TABLE_OWNER</span></span>|<span data-ttu-id="c497f-448">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="c497f-448">String</span></span>|  
|<span data-ttu-id="c497f-449">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="c497f-449">TABLE_NAME</span></span>|<span data-ttu-id="c497f-450">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="c497f-450">String</span></span>|  
|<span data-ttu-id="c497f-451">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="c497f-451">COLUMN_NAME</span></span>|<span data-ttu-id="c497f-452">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="c497f-452">String</span></span>|  
|<span data-ttu-id="c497f-453">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="c497f-453">DATA_TYPE</span></span>|<span data-ttu-id="c497f-454">Int16</span><span class="sxs-lookup"><span data-stu-id="c497f-454">Int16</span></span>|  
|<span data-ttu-id="c497f-455">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="c497f-455">TYPE_NAME</span></span>|<span data-ttu-id="c497f-456">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="c497f-456">String</span></span>|  
|<span data-ttu-id="c497f-457">PRECISION</span><span class="sxs-lookup"><span data-stu-id="c497f-457">PRECISION</span></span>|<span data-ttu-id="c497f-458">Int32</span><span class="sxs-lookup"><span data-stu-id="c497f-458">Int32</span></span>|  
|<span data-ttu-id="c497f-459">LENGTH</span><span class="sxs-lookup"><span data-stu-id="c497f-459">LENGTH</span></span>|<span data-ttu-id="c497f-460">Int32</span><span class="sxs-lookup"><span data-stu-id="c497f-460">Int32</span></span>|  
|<span data-ttu-id="c497f-461">SCALE</span><span class="sxs-lookup"><span data-stu-id="c497f-461">SCALE</span></span>|<span data-ttu-id="c497f-462">Int16</span><span class="sxs-lookup"><span data-stu-id="c497f-462">Int16</span></span>|  
|<span data-ttu-id="c497f-463">RADIX</span><span class="sxs-lookup"><span data-stu-id="c497f-463">RADIX</span></span>|<span data-ttu-id="c497f-464">Int16</span><span class="sxs-lookup"><span data-stu-id="c497f-464">Int16</span></span>|  
|<span data-ttu-id="c497f-465">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="c497f-465">NULLABLE</span></span>|<span data-ttu-id="c497f-466">Int16</span><span class="sxs-lookup"><span data-stu-id="c497f-466">Int16</span></span>|  
|<span data-ttu-id="c497f-467">REMARKS</span><span class="sxs-lookup"><span data-stu-id="c497f-467">REMARKS</span></span>|<span data-ttu-id="c497f-468">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="c497f-468">String</span></span>|  
|<span data-ttu-id="c497f-469">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="c497f-469">ORDINAL_POSITION</span></span>|<span data-ttu-id="c497f-470">Int32</span><span class="sxs-lookup"><span data-stu-id="c497f-470">Int32</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="c497f-471">Verfahren</span><span class="sxs-lookup"><span data-stu-id="c497f-471">Procedures</span></span>  
  
|<span data-ttu-id="c497f-472">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="c497f-472">ColumnName</span></span>|<span data-ttu-id="c497f-473">DataType</span><span class="sxs-lookup"><span data-stu-id="c497f-473">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="c497f-474">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="c497f-474">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="c497f-475">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="c497f-475">String</span></span>|  
|<span data-ttu-id="c497f-476">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="c497f-476">PROCEDURE_OWNER</span></span>|<span data-ttu-id="c497f-477">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="c497f-477">String</span></span>|  
|<span data-ttu-id="c497f-478">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="c497f-478">PROCEDURE_NAME</span></span>|<span data-ttu-id="c497f-479">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="c497f-479">String</span></span>|  
|<span data-ttu-id="c497f-480">NUM_INPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="c497f-480">NUM_INPUT_PARAMS</span></span>|<span data-ttu-id="c497f-481">Int16</span><span class="sxs-lookup"><span data-stu-id="c497f-481">Int16</span></span>|  
|<span data-ttu-id="c497f-482">NUM_OUTPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="c497f-482">NUM_OUTPUT_PARAMS</span></span>|<span data-ttu-id="c497f-483">Int16</span><span class="sxs-lookup"><span data-stu-id="c497f-483">Int16</span></span>|  
|<span data-ttu-id="c497f-484">NUM_RESULT_SETS</span><span class="sxs-lookup"><span data-stu-id="c497f-484">NUM_RESULT_SETS</span></span>|<span data-ttu-id="c497f-485">Int16</span><span class="sxs-lookup"><span data-stu-id="c497f-485">Int16</span></span>|  
|<span data-ttu-id="c497f-486">REMARKS</span><span class="sxs-lookup"><span data-stu-id="c497f-486">REMARKS</span></span>|<span data-ttu-id="c497f-487">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="c497f-487">String</span></span>|  
|<span data-ttu-id="c497f-488">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="c497f-488">PROCEDURE_TYPE</span></span>|<span data-ttu-id="c497f-489">Int16</span><span class="sxs-lookup"><span data-stu-id="c497f-489">Int16</span></span>|  
  
### <a name="procedurecolumns"></a><span data-ttu-id="c497f-490">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="c497f-490">ProcedureColumns</span></span>  
  
|<span data-ttu-id="c497f-491">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="c497f-491">ColumnName</span></span>|<span data-ttu-id="c497f-492">DataType</span><span class="sxs-lookup"><span data-stu-id="c497f-492">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="c497f-493">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="c497f-493">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="c497f-494">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="c497f-494">String</span></span>|  
|<span data-ttu-id="c497f-495">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="c497f-495">PROCEDURE_OWNER</span></span>|<span data-ttu-id="c497f-496">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="c497f-496">String</span></span>|  
|<span data-ttu-id="c497f-497">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="c497f-497">PROCEDURE_NAME</span></span>|<span data-ttu-id="c497f-498">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="c497f-498">String</span></span>|  
|<span data-ttu-id="c497f-499">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="c497f-499">COLUMN_NAME</span></span>|<span data-ttu-id="c497f-500">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="c497f-500">String</span></span>|  
|<span data-ttu-id="c497f-501">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="c497f-501">COLUMN_TYPE</span></span>|<span data-ttu-id="c497f-502">Int16</span><span class="sxs-lookup"><span data-stu-id="c497f-502">Int16</span></span>|  
|<span data-ttu-id="c497f-503">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="c497f-503">DATA_TYPE</span></span>|<span data-ttu-id="c497f-504">Int16</span><span class="sxs-lookup"><span data-stu-id="c497f-504">Int16</span></span>|  
|<span data-ttu-id="c497f-505">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="c497f-505">TYPE_NAME</span></span>|<span data-ttu-id="c497f-506">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="c497f-506">String</span></span>|  
|<span data-ttu-id="c497f-507">PRECISION</span><span class="sxs-lookup"><span data-stu-id="c497f-507">PRECISION</span></span>|<span data-ttu-id="c497f-508">Int32</span><span class="sxs-lookup"><span data-stu-id="c497f-508">Int32</span></span>|  
|<span data-ttu-id="c497f-509">LENGTH</span><span class="sxs-lookup"><span data-stu-id="c497f-509">LENGTH</span></span>|<span data-ttu-id="c497f-510">Int32</span><span class="sxs-lookup"><span data-stu-id="c497f-510">Int32</span></span>|  
|<span data-ttu-id="c497f-511">SCALE</span><span class="sxs-lookup"><span data-stu-id="c497f-511">SCALE</span></span>|<span data-ttu-id="c497f-512">Int16</span><span class="sxs-lookup"><span data-stu-id="c497f-512">Int16</span></span>|  
|<span data-ttu-id="c497f-513">RADIX</span><span class="sxs-lookup"><span data-stu-id="c497f-513">RADIX</span></span>|<span data-ttu-id="c497f-514">Int16</span><span class="sxs-lookup"><span data-stu-id="c497f-514">Int16</span></span>|  
|<span data-ttu-id="c497f-515">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="c497f-515">NULLABLE</span></span>|<span data-ttu-id="c497f-516">Int16</span><span class="sxs-lookup"><span data-stu-id="c497f-516">Int16</span></span>|  
|<span data-ttu-id="c497f-517">REMARKS</span><span class="sxs-lookup"><span data-stu-id="c497f-517">REMARKS</span></span>|<span data-ttu-id="c497f-518">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="c497f-518">String</span></span>|  
|<span data-ttu-id="c497f-519">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="c497f-519">OVERLOAD</span></span>|<span data-ttu-id="c497f-520">Int32</span><span class="sxs-lookup"><span data-stu-id="c497f-520">Int32</span></span>|  
|<span data-ttu-id="c497f-521">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="c497f-521">ORDINAL_POSITION</span></span>|<span data-ttu-id="c497f-522">Int32</span><span class="sxs-lookup"><span data-stu-id="c497f-522">Int32</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="c497f-523">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="c497f-523">ProcedureParameters</span></span>  
  
|<span data-ttu-id="c497f-524">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="c497f-524">ColumnName</span></span>|<span data-ttu-id="c497f-525">DataType</span><span class="sxs-lookup"><span data-stu-id="c497f-525">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="c497f-526">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="c497f-526">PROCEDURE_CAT</span></span>|<span data-ttu-id="c497f-527">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="c497f-527">String</span></span>|  
|<span data-ttu-id="c497f-528">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="c497f-528">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="c497f-529">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="c497f-529">String</span></span>|  
|<span data-ttu-id="c497f-530">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="c497f-530">PROCEDURE_NAME</span></span>|<span data-ttu-id="c497f-531">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="c497f-531">String</span></span>|  
|<span data-ttu-id="c497f-532">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="c497f-532">COLUMN_NAME</span></span>|<span data-ttu-id="c497f-533">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="c497f-533">String</span></span>|  
|<span data-ttu-id="c497f-534">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="c497f-534">COLUMN_TYPE</span></span>|<span data-ttu-id="c497f-535">Int16</span><span class="sxs-lookup"><span data-stu-id="c497f-535">Int16</span></span>|  
|<span data-ttu-id="c497f-536">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="c497f-536">DATA_TYPE</span></span>|<span data-ttu-id="c497f-537">Int16</span><span class="sxs-lookup"><span data-stu-id="c497f-537">Int16</span></span>|  
|<span data-ttu-id="c497f-538">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="c497f-538">TYPE_NAME</span></span>|<span data-ttu-id="c497f-539">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="c497f-539">String</span></span>|  
|<span data-ttu-id="c497f-540">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="c497f-540">COLUMN_SIZE</span></span>|<span data-ttu-id="c497f-541">Int32</span><span class="sxs-lookup"><span data-stu-id="c497f-541">Int32</span></span>|  
|<span data-ttu-id="c497f-542">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="c497f-542">BUFFER_LENGTH</span></span>|<span data-ttu-id="c497f-543">Int32</span><span class="sxs-lookup"><span data-stu-id="c497f-543">Int32</span></span>|  
|<span data-ttu-id="c497f-544">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="c497f-544">DECIMAL_DIGITS</span></span>|<span data-ttu-id="c497f-545">Int16</span><span class="sxs-lookup"><span data-stu-id="c497f-545">Int16</span></span>|  
|<span data-ttu-id="c497f-546">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="c497f-546">NUM_PREC_RADIX</span></span>|<span data-ttu-id="c497f-547">Int16</span><span class="sxs-lookup"><span data-stu-id="c497f-547">Int16</span></span>|  
|<span data-ttu-id="c497f-548">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="c497f-548">NULLABLE</span></span>|<span data-ttu-id="c497f-549">Int16</span><span class="sxs-lookup"><span data-stu-id="c497f-549">Int16</span></span>|  
|<span data-ttu-id="c497f-550">REMARKS</span><span class="sxs-lookup"><span data-stu-id="c497f-550">REMARKS</span></span>|<span data-ttu-id="c497f-551">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="c497f-551">String</span></span>|  
|<span data-ttu-id="c497f-552">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="c497f-552">COLUMN_DEF</span></span>|<span data-ttu-id="c497f-553">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="c497f-553">String</span></span>|  
|<span data-ttu-id="c497f-554">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="c497f-554">SQL_DATA_TYPE</span></span>|<span data-ttu-id="c497f-555">Int16</span><span class="sxs-lookup"><span data-stu-id="c497f-555">Int16</span></span>|  
|<span data-ttu-id="c497f-556">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="c497f-556">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="c497f-557">Int16</span><span class="sxs-lookup"><span data-stu-id="c497f-557">Int16</span></span>|  
|<span data-ttu-id="c497f-558">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="c497f-558">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="c497f-559">Int32</span><span class="sxs-lookup"><span data-stu-id="c497f-559">Int32</span></span>|  
|<span data-ttu-id="c497f-560">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="c497f-560">ORDINAL_POSITION</span></span>|<span data-ttu-id="c497f-561">Int32</span><span class="sxs-lookup"><span data-stu-id="c497f-561">Int32</span></span>|  
|<span data-ttu-id="c497f-562">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="c497f-562">IS_NULLABLE</span></span>|<span data-ttu-id="c497f-563">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="c497f-563">String</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c497f-564">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c497f-564">See Also</span></span>  
 [<span data-ttu-id="c497f-565">ADO.NET Managed Provider und DataSet Developer Center</span><span class="sxs-lookup"><span data-stu-id="c497f-565">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
