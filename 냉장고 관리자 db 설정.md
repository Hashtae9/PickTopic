# 냉장고 관리자 db 설정

## USER

```
CREATE TABLE refrigeratormanager.`user` (
	USER_ID varchar(100) NOT NULL,
	USER_PWD varchar(100) NOT NULL,
	USER_NAME varchar(100) NOT NULL,
	USER_PHONE varchar(100) NULL,
	USER_EMAIL varchar(100) NULL,
	USER_BIRTH DATE NOT NULL,
	ENROLL_DATE DATE NULL,
	LOGIN_TYPE varchar(100) NULL,
	CONSTRAINT user_pk PRIMARY KEY (USER_ID)
)
ENGINE=InnoDB
DEFAULT CHARSET=utf8mb4
COLLATE=utf8mb4_0900_ai_ci;

```



## 냉장고

```
CREATE TABLE refrigeratormanager.refrigerator (
	refri_seq INTEGER auto_increment NOT NULL,
	refri_name varchar(100) NULL,
	refri_date DATE NULL,
	fk_user_id varchar(100) NOT NULL,
	CONSTRAINT refrigerator_pk PRIMARY KEY (refri_seq),
	CONSTRAINT refrigerator_FK FOREIGN KEY (fk_user_id) REFERENCES refrigeratormanager.`user`(USER_ID) ON DELETE RESTRICT ON UPDATE CASCADE
)
ENGINE=InnoDB
DEFAULT CHARSET=utf8mb4
COLLATE=utf8mb4_0900_ai_ci;
```



## 냉장고 재료

```
CREATE TABLE refrigeratormanager.ingre_refri (
	fk_refri_seq INT UNSIGNED NOT NULL,
	fk_ingre_seq INT UNSIGNED NOT NULL,
	ingre_expir_date DATE NULL,
	frozen BOOL NULL
)
ENGINE=InnoDB
DEFAULT CHARSET=utf8mb4
COLLATE=utf8mb4_0900_ai_ci;

```



## 재료

+ 재료를 레시피 재료를 우선으로 번호 매핑

```
CREATE TABLE refrigeratormanager.INGREDIENT (
	ingre_seq BIGINT UNSIGNED auto_increment NOT NULL,
	ingre_name varchar(100) NOT NULL,
	CONSTRAINT INGREDIENT_pk PRIMARY KEY (ingre_seq)
)
ENGINE=InnoDB
DEFAULT CHARSET=utf8mb4
COLLATE=utf8mb4_0900_ai_ci;

```



## 레시피

```
CREATE TABLE refrigeratormanager.recipe (
	rec_seq INTEGER UNSIGNED auto_increment NOT NULL,
	rec_title varchar(100) NOT NULL,
	rec_date DATE NULL,
	rec_description varchar(1000) NULL,
	rec_link varchar(100) NULL,
	rec_view INTEGER NULL,
	rec_category varchar(100) NULL,
	CONSTRAINT recipe_pk PRIMARY KEY (rec_seq)
)
ENGINE=InnoDB
DEFAULT CHARSET=utf8mb4
COLLATE=utf8mb4_0900_ai_ci;
```



## 재료_레시피

```
CREATE TABLE refrigeratormanager.ingre_recipe (
	FK_RECIPE_SEQ INTEGER NOT NULL,
	FK_INGRE_SEQ INT NOT NULL
)
ENGINE=InnoDB
DEFAULT CHARSET=utf8mb4
COLLATE=utf8mb4_0900_ai_ci;

```

