# SUMMARY

장고 프레임워크 기반의 블로그 개발

# WBS

```mermaid

gantt
    title BLOG (feat. Django)
    dateFormat  MM-DD
    section 저장소 세팅
    리포지토리 생성     :a1, 08-26, 1d
    section 환경 구축
    WBS 작성, 프로젝트 아이디어 기획 :a2, 08-27, 3d
    ERD 생성 :a3, 08-31, 1d
    section 구현
    모델 구현, CRUD 구현 :a4, 09-02, 1d
    인증 구현           :a5, 09-02, 1d
    section 검토
    검토               :a6, 09-02, 1d
```

# URL

| 역할        | URL                        | 앱       |
| :---------- | :------------------------- | :------- |
| 메인        | /                          | main     |
| 로그인      | /accounts/login            | accounts |
| 로그아웃    | /accounts/logout           | accounts |
| 게시글 목록 | /blog                      | blog     |
| 게시글 상세 | /blog/<int:post_pk>        | blog     |
| 게시글 작성 | /blog/write                | blog     |
| 게시글 수정 | /blog/edit/<int:post_pk>   | blog     |
| 게시글 삭제 | /blog/delete/<int:post_pk> | blog     |
| 게시글 검색 | /blog?q='검색어'           | blog     |

# DB

```mermaid
erDiagram
    Account {
        char email PK
        char nickname
    }

    Post {
        char title
        char content
        img thumbnail_image
        file file_upload
        date created_at
        date updated_at
        char author FK "Reference to Account's email"
    }

    Account ||--o{ Post : "writes"
```

# DEMO

시연 영상

# ISSUE

- mermaid 를 VS CODE에서 미리 보기 하려면?

  Markdown Preview Mermaid Support 확장 프로그램 설치
