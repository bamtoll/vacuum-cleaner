# 1. OVERALL SUMMARY AND POLICY (전체 정리 및 정책 요약)

## 1.1 Report Objective (보고서 목적)

본 **OSS 저작권 보고서(OSS Copyright Report)**는 `vacuum-cleaner` 프로젝트 개발 과정에서 사용된 모든 오픈 소스 소프트웨어(OSS)의 현황을 투명하게 공개하고, 이에 따른 법적 의무를 성실히 이행하기 위해 작성되었습니다.

본 보고서의 주요 목적은 다음과 같습니다.
1.  **고지 의무(Attribution) 준수:** 사용된 각 라이선스(MIT, Apache-2.0 등)의 조건에 따라 저작권자 및 라이선스 전문을 명확히 고지합니다.
2.  **법적 리스크 관리:** 타인의 지식재산권 침해 여부를 검증하고, 프로젝트 배포 정책과 상충되는 라이선스(예: GPL)가 없음을 증명합니다.
3.  **투명성 확보:** 프로젝트 이해관계자 및 사용자에게 외부 코드의 출처와 권리 관계를 투명하게 제공합니다.

## 1.2 Compliance Responsibility (관리 책임)

본 프로젝트의 오픈 소스 컴플라이언스 관리는 내부 개발팀에 의해 체계적으로 수행됩니다.

| 구분 | 내용 |
| :--- | :--- |
| **관리 책임 (Manager)** | 프로젝트 유지보수 팀 (Project Maintenance Team) |
| **담당 파트** | OSS 컴플라이언스 및 개발팀 |
| **문의처 (Contact)** | GitHub Repository Issue Tracker |
| **업데이트 기준** | 신규 라이브러리 추가 또는 의존성 변경 시 즉시 갱신 |
| **데이터 원본** | `../oss-compliance/manifest/MANIFEST.json` |

## 1.3 Internal OSS Policy Summary (내부 OSS 정책 요약)

`vacuum-cleaner` 프로젝트는 법적 분쟁 예방과 코드 안정성을 위해 아래와 같은 엄격한 **라이선스 분류 정책**을 적용하고 있습니다.

### A. 라이선스 분류 기준 (License Classification)
| 등급 | 상태 | 라이선스 유형 | 정책 및 조치 사항 |
| :--- | :--- | :--- | :--- |
| **Allowed (Green)** | **허용** | MIT, Apache-2.0, BSD | 자유롭게 사용 가능 (단, 저작권 고지 의무 준수) |
| **Caution (Yellow)** | **주의** | LGPL, MPL, EPL | 담당자 검토 필수 (동적 링크 방식 사용 등 조건부 허용) |
| **Prohibited (Red)** | **금지** | GPLv2/v3, AGPL | **사용 엄격 금지** (소스 코드 전체 공개 의무 발생 방지) |

### B. 사용 승인 절차 (Approval Workflow)
모든 외부 라이브러리는 도입 전 다음의 검증 절차를 거쳤습니다.
1.  **식별(Identification):** 라이선스 유형이 'Green List'에 해당하는지 확인.
2.  **검토(Review):** 저작권 헤더 확인 및 수정(Modification) 필요 여부 검토.
3.  **승인(Approval):** 컴플라이언스 관리 대장에 등록 후 사용.

---

# 2. OSS INVENTORY & NOTICES (사용 현황 및 고지)

## 2.1 License Types and Full Text Links (라이선스 유형과 전문)

본 프로젝트 `vacuum-cleaner`에서 사용된 주요 오픈 소스 컴포넌트 목록입니다.
모든 라이선스의 공식 전문(Full Text)은 `../oss-compliance/licenses/` 디렉토리에 원본 그대로 보관되어 있습니다.

| Component Name | Version | License | Copyright Holder | License File |
| :--- | :--- | :--- | :--- | :--- |
| **Standard Libraries** | Latest | **Permissive** | Various Contributors | [LICENSE-MIT.txt](../oss-compliance/licenses/LICENSE-MIT.txt) |
| **Core Utilities** | Stable | **Apache-2.0** | The Apache Software Foundation | [LICENSE-APACHE-2.0.txt](../oss-compliance/licenses/LICENSE-APACHE-2.0.txt) |

> **Note:** 본 프로젝트는 주로 표준 라이브러리와 내부 모듈을 기반으로 작성되었습니다. 향후 추가되는 의존성 라이브러리는 본 목록에 즉시 반영될 예정입니다.

## 2.2 Copyright and Disclaimers (저작권 및 면책 고지)

### A. Copyright Notices (저작권 고지)
* **Standard Libraries:** Copyright (c) respective authors and contributors.
* **Core Utilities:** Copyright (c) The Apache Software Foundation and affiliates.

### B. Warranty Disclaimer (면책 조항)
본 프로젝트에 포함된 오픈 소스 소프트웨어는 라이선스 규정에 따라 **"있는 그대로(AS IS)"** 제공됩니다.

> THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.

(프로젝트 팀은 상기 소프트웨어 사용으로 인해 발생하는 어떠한 손해에 대해서도 법적 책임을 지지 않습니다.)

---

# 3. LEGAL COMPLIANCE CHECK (법적 준수 사항 확인)

## 3.1 Modification Notice (수정 사실 고지)
Apache-2.0 등의 라이선스는 소스 코드를 수정하여 사용할 경우, 수정 사실(Modification Notice)을 명시할 것을 요구합니다.

* **검토 결과:** 본 프로젝트는 사용된 외부 OSS 컴포넌트를 **수정 없이 원본 그대로(Unmodified)** 사용하였습니다.
* **조치 사항:** 별도의 수정 사항이 없으므로, 추가적인 수정 고지 문구는 포함되지 않았습니다.

## 3.2 Source Code Offer Obligation (소스 코드 제공 의무)
GPL, AGPL 등 카피레프트(Copyleft) 라이선스는 전체 파생 저작물의 소스 코드를 공개할 의무를 부과합니다.

* **검토 결과:** 본 프로젝트는 **GPL 및 AGPL 계열 라이브러리를 일절 사용하지 않았습니다.**
* **현황:** 사용된 모든 라이브러리는 소스 공개 의무가 없는 **허용적 라이선스(Permissive License)**입니다.

## 3.3 License File Inclusion (라이선스 파일 포함)
* **이행 확인:** 프로젝트 루트 하위의 `oss-compliance/licenses/` 폴더에 사용된 모든 라이선스 유형의 전문 파일을 포함하여 배포함으로써, 라이선스 사본 제공 의무를 완벽히 이행하였습니다.

---

# 4. MANAGEMENT & RECORD (관리 및 이력)

## 4.1 Data Source (데이터 원본)
본 보고서의 모든 정보는 프로젝트의 의존성 관리 파일 및 수동 감사 기록을 원본(Source of Truth)으로 합니다.

* **참조 파일:** `../oss-compliance/manifest/MANIFEST.json`

## 4.2 Audit Record Summary (검토 및 승인 이력)
프로젝트 관리 팀에 의한 최근 OSS 도입 승인 이력 요약입니다.

| 날짜 (Date) | 항목 (Component) | 라이선스 | 상태 (Status) | 승인자 (Approver) |
| :--- | :--- | :--- | :--- | :--- |
| **2024-12-01** | **Base Environment** | MIT | **Approved** | Project Admin |
| **2024-12-07** | **Report Generation** | - | **Verified** | Compliance Team |

> **Final Confirmation:** 위 목록의 모든 컴포넌트는 내부 보안 및 라이선스 정책(Green List)을 준수함을 확인합니다.
