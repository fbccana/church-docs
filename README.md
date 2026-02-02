# church-docs

## Organizational Chart

graph TD

    %% Top Governance
    PC[Personnel Committee] --> SP[Senior Pastor]
    CO[Corporate Officers] --> SP

    %% Ministerial Staff (Direct Reports to Senior Pastor)
    SP --> Admin[Admin]
    SP --> Music[Music]
    SP --> Youth[Youth]
    SP --> Children[Children]
    SP --> HP[Hispanic Pastor]

    %% Support Staff - All Primary Reports to Admin (solid lines)
    Admin --> CS[Church Sec]
    Admin --> FS[Financial Sec]
    Admin --> MS[Music Sec]
    Admin --> FLC1[FLC One]
    Admin --> FLC2[FLC Two]
    Admin --> Media[Media Sec]
    Admin --> FM[Facility Mgr]
    Admin --> MC[Main Custodian]
    Admin --> CC[Child Custodian]
    Admin --> FC[FLC Custodian]

    %% Program Staff - Primary to relevant ministers/support
    Admin --> Kitchen[Kitchen]
    Music --> Pianist[Pianist]
    Music --> Organist[Organist]
    Children --> KDO[KDO]
    Children --> Nursery[Nursery]
    Children --> ASC[ASC]

    %% Secondary Support Relationships (dotted lines for functional support)
    MS -.->|"supports"| Music
    FLC1 -.->|"supports"| Youth
    FLC2 -.->|"supports"| Children
    Media -.->|"supports"| Music
    %% Add more if needed, e.g.:
    %% CS -.->|"supports"| SP
    %% FS -.->|"supports"| Admin
