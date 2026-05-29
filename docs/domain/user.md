# Entity: User
_@Entity_  
_@Table(name = "app_users")_

## <u>Purpose:</u>
Represents a person who owns or manages vehicles in the DashIQ system.

### <u>Fields:</u>
* private Long id
  * _@Id_
  * _@GeneratedValue(strategy = GenerationType.IDENTITY)_
* private String firstName
* private String lastName
* private String email
  * _@Column(nullable = false, unique = true)_
* private String phoneNumber
* private LocalDateTime createdAt
* private LocalDateTime updatedAt

### <u>Relationships:</u>
* A User can own many Vehicles. (OneToMany)
* A User may receive many Notifications. (OneToMany)
* A User may have many Maintenance Records through their Vehicles. (OneToMany)

### <u>Business Rules:</u>
* Email is required
* Email must be unique
* First name is required
* Last name is required
* Phone number is optional for MVP
* Phone number may be used later for verification and notifications

### <u>MVP NOTES</u>

_For the MVO, the User exits mainly to own vehicle records, Authentication, roles, subscriptions, and marketing preferences are deferred._