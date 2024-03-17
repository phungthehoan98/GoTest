# GoTest
Go Test for the new language

# SQL:
    mysql -u root -p

    CREATE DATABASE snippetbox CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci;

    USE snippetbox;

    CREATE TABLE snippets (
    id INTEGER NOT NULL PRIMARY KEY AUTO_INCREMENT,
    title VARCHAR(100) NOT NULL,
    content TEXT NOT NULL,
    created DATETIME NOT NULL,
    expires DATETIME NOT NULL
    );
    CREATE INDEX idx_snippets_created ON snippets(created);

    CREATE TABLE users (
    id INTEGER NOT NULL PRIMARY KEY AUTO_INCREMENT,
    name VARCHAR(255) NOT NULL,
    email VARCHAR(255) NOT NULL,
    hashed_password CHAR(60) NOT NULL,
    created DATETIME NOT NULL
    );
    ALTER TABLE users ADD CONSTRAINT users_uc_email UNIQUE (email);

# Generate Self-Signed TLS Certificate generate_cert.go (https://localhost:4000)
    cd tls && go run /usr/local/go/src/crypto/tls/generate_cert.go --rsa-bits=2048 --host=localhost
     
# Start: 
    export SNIPPETBOX_ADDR=":9999"
    go run cmd/web/* -addr=$SNIPPETBOX_ADDR
# Note: 
    9999 is your port want to use (https://localhost:9999/)
